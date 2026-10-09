# Análise — região de Santo Antônio de Lisboa (Sâncão + Sambaqui + Cacupé)

Análise de seções eleitorais (Presidente) de **Florianópolis/SC, zona 100**, para os
locais de votação da região de **Santo Antônio de Lisboa**, composta pelos bairros
**Cacupé + Santo Antônio de Lisboa (Sâncão) + Sambaqui**. Eleições 2018 (2 turnos),
2022 (2 turnos) e 2026 (1º turno). Estrutura de vira-voto Flávio → Lula:
ver `estrategia-flip-santo-antonio.md`.

Data da análise: 2026-10-09. Fontes: TSE (arquivos `_BR` federais) + planos de
governo em `dados/planos/` (txt extraído; sha256 no `dados/planos/README.md`).

## Escopo e locais

### Fato geográfico (OSM)

No OpenStreetMap, **Sambaqui e Cacupé são sub-bairros** que aparecem sob o bairro
"Santo Antônio de Lisboa" na cadeia de endereços (Nominatim devolve
`display_name` com `… Sambaqui, Florianópolis` / `… Cacupé, Florianópolis`, sem
campo `address.suburb` próprio). A revisão manual de cada local abaixo usa essa
cadeia completa como referência de bairro.

### Locais de votação incluídos

| local | nome | endereço (TSE) | bairro (revisão) | anos | observação |
|---|---|---|---|---|---|
| 1210 | EBM Paulo Fontes | Rua Prof. Osni Barbato, 168 | Sâncão (OSM: Sâncão Oeste) | 2018/2022/2026 | 8→9 seções; 3.122 aptos em 2026 |
| 1228 | NEI Maria Salomé dos Santos | Rua Prof. Euclides da Cunha s/n | Sambaqui (OSM: "Rua Professor Euclides Pires da Cunha, Sambaqui") | 2018/2022/2026 | 4→5 seções (sec. 455 criada em 2022) |
| 1880 | NEIM Altino Dealtino Cabral | Rua Padre Lourenço Rodrigues de Andrade, 120 | Sâncão (OSM: Sâncão Oeste) | **2026** | 1 seção, 161 aptos; em 2018 o local 1880 estava em outra zona (fora do filtro zona 100); ausente em 2022 (escola fechada para eleição naquele ano) |
| 1589 (só 2018) | (2018) Escola Desdobrada Marcolino José de Lima | BR-101 (Isidoro Dutra), 1200 | Barra do Sambaqui | **2018** | rodada de sensibilidade separada (`detalhe_marcolino.csv`): em 2022/2026 o local 1589 é outro prédio (Conselho Comunitário Saco dos Limões) — colisão de ID de local entre anos |

### Limitação declarada: Cacupé

**Nenhum local de votação foi identificado para Cacupé** (2018/2022/2026) dentro da
zona 100: nenhuma escola do bairro aparece como local nas listas TSE do município
para os três anos. Os eleitores de Cacupé votam nas escolas da região (Sambaqui/
Sâncão), o que já está captado nos locais 1210/1228/1880. Declaramos isso como
limitação do recorte, não como buraco de dados.

### Excluídos (revisão manual, zona 100)

| local | por quê |
|---|---|
| 1244 Mâncio Costa; 1252 (2018) | Ratones (POI de escola no OSM) |
| 1260; 1597-2018 | Cachoeira do Bom Jesus (continente) |
| 1317; 1776 | Jurerê (OSM: "Rodovia Tertuliano Brito Xavier, Jurerê Leste") |
| 1325 | Cachoeira do Bom Jesus/Ingleses (baixa confiança; fora da região) |
| 1341 | continente |
| 1368; 1376; 1384; 1643; 1732; 1830; 1929 | Rio Vermelho/Ingleses → análise `dados/analise_norte_floripa/` |
| 1406 | Pântano do Sul |
| 1473; 1627; 1724; 1872; 1902 | Canasvieiras (Rod. Virgílio Várzea) |
| 1597-2026 | Tapera da Base (Rod. Açoriana) |
| 1759-2026 | Pantanal/Trindade |
| 1570 | Campeche (SC-405 = rodovia Campeche) |
| 1155; 1740; 1791; 1910 | Trindade (Av. Madre Benvenuta) |

Zonas 12/13/14 do município foram verificadas: nenhum local cai na região.

## Dados e decomposição

- `votos.tsv` / `aptos.tsv`: extração principal (locais 1210/1880/1228) via
  `03_votos.py` / `04_aptos.py` (skill `flip-flavio-lula`).
- `votos_marcolino.tsv` / `aptos_marcolino.tsv`: rodada 2018 do local 1589
  (`config_marcolino.json` — só o arquivo 2018, para não misturar o prédio
  Saco dos Limões de 2022/26).
- Classificação dos "outros": **C** = centro (3º candidato da região: 2018
  Ciro; 2022 Sinval; 2026 Zema+Renan Santos na definição da skill — aqui,
  `dir3` = {ZEMA, RENAN SANTOS} só em 2026), **E** = 3º de esquerda (Boulos 2022),
  **N** = 3º de direita (Zema 2026), **BN** = branco+nulo. Ordem de classificação:
  L → R → BN → E → N → C (resto). Convenção registrada em
  `references/tse-data.md` da skill.
- `detalhe_por_secao.csv` (18 colunas) e `relatorio.txt`: saída do `05_analise.py`.
  `detalhe_marcolino.csv`: sensibilidade 2018.

### Validação

- `T` (soma de votos por seção no `votos.tsv`) == `QT_COMPARECIMENTO` do
  `detalhe_votacao_secao_<ANO>_BR.csv` (SC/FLORIANÓPOLIS/zona 100/locais do recorte/
  cargo Presidente): **71/71 linhas OK** (2018: 28, 2022: 26, 2026: 17).
- `aptos >= T` em todas as seções: OK.
- Revisão geográfica local por local: tabela acima (revisão manual registrada).

## Cartas-conceito (mineração dos planos)

Regra: busca **somente nos txt** de `dados/planos/` (marcador `=== PAGINA N ===`,
N = página do PDF). Contagens com **fronteira de palavra** (ex.: "MEI" não casa
"meio"). Carta = necessidade + variantes superficiais + variantes de intenção +
mecanismo esperado; classificação A (cobertura explícita c/ valor) / B (menção
genérica) / C (incoerência interna) / D (lacuna: 0 em todas as variantes).

| # | Perfil | Necessidade | Variantes verificadas (contagem F / L) | Classe F | Contraponto L |
|---|---|---|---|---|---|
| P1 | Pescador (Sambaqui) | pesca artesanal | pesca, pescador, pescado, pesqueiro, portinho, camarão, sambaqui, frota (0/…); aquicultura, territórios pesqueiros (0/1) | **D** (10 variantes, 0 no plano F) | **A** p.61: "fomento à pesca artesanal e à aquicultura familiar… Plano Nacional da Pesca Artesanal (PNPA)… proteção dos territórios pesqueiros, da sociobiodiversidade e dos modos de vida das comunidades das águas" |
| P2 | Moradia (Sambaqui/Cacupé) | casa própria + regularização + saneamento | moradia 2, habitação 2, casa própria 6, minha casa 0, casa verde e amarela 1, **favela 0, periferia 0**, encosta 1, escritura 3, fundiária 3, urbanizaç* 2 (F) | **A/B** p.47 (CVA 2,5 mi + "menor taxa de juros possível" + "áreas sob domínio de facções" + "urbanização de áreas degradadas" + saneamento) + **D** para favela/periferia | **A** p.45 (MCMV: 2 mi adiantadas → 3 mi; "mais de 80% das obras que estavam paralisadas já foram retomadas"; 1 mi quitadas para BF/BPC) + **A** p.46 (R$ 23,3 bi saneamento; "priorizar periferias historicamente negligenciadas"); p.28 urbanização de favelas/periferias (sem valor na linha; o R$ 10 bi FIIS das pp.27-28 é do programa de segurança) |
| P3 | Salário/custo de vida (todos) | salário mínimo + poder de compra | **salário mínimo 0** (F), "salários mínimos" 1 (p.29, diagnóstico de dívida), salário 7, cesta básica 0, rotativo 1 (p.32), endividad* 1 (p.29), **bolsa 0, bolsa família 0**, bolsas 3 (todas esportes/formação: pp.6, 36, 40), programa(s) social(is) 3+3 (pp.9, 33, 42, 43, 54), assist* 5 | **D** (salário mínimo; bolsa família) + **B** (p.9 "Manteremos e aperfeiçoaremos os programas sociais"; p.42 "manter os programas sociais existentes… o programa social é o começo da caminhada, não o fim"; p.43 beneficiário "terá prioridade em todas as ações do Estado voltadas ao trabalho") | p.74 "continuidade à política de valorização do salário mínimo como meio estratégico de distribuição de renda"; bolsa família 4 (pp.12, 24, 45, 58); p.12 "recriado e expandido com benefícios especiais" |
| P4 | Indústria/MEI (Cacupé) | indústria local + crédito pequeno | indústria 8 (todas genéricas: pp.16, 36, 49, 52, 53, 55, 56, 60), industrial 0, fábrica 2 (genéricas: pp.31, 53), emprego 32, **MEI 0**, pequeno negócio 3, pequenas empresas 0 (F) | **B** (ex.: p.52 "energia abundante e barata é conta de luz menor e indústria de portas abertas"; p.56 "indústria, agronegócio, saúde e logística") + **D** (MEI) | **A** p.57: "O Pronampe já atingiu 1,6 milhão de operações e o Procred 360 outras 211 mil, mobilizando um montante de R$ 130 bilhões. Criamos a plataforma MEI Conta Com a Gente" |
| P5 | Mobilidade ilha↔continente (Cacupé/Sambaqui) | ponte/BR-101 + ônibus | ônibus 2, transporte 11, mobilidade 5, trânsito 2, **ponte 0, BR-101 0** (F e L), rodovia 2, deslocamento 1, trilhos 2, metrô 1 (F) | **B** p.51 ("Milhões de brasileiros perdem, todo dia, horas dentro de um ônibus lotado… tempo roubado"; "reduzir o deslocamento da população"; "linhas de metrô, transporte sobre trilhos e ônibus movidos a eletricidade") + **A** p.51 (R$ 900 bi — mas nos "corredores de escoamento do Centro-Oeste até os portos", Ferrogrão, "trem de cargas… Mato Grosso, o oeste do Paraná e Santa Catarina", Trem do Nordeste, Tapajós) + **D** (ponte, BR-101) | **A** p.46: "mais 233 km de metrôs, trens e VLTs e outros 296 km de corredores exclusivos de ônibus no padrão BRT… renovar a frota de ônibus de 144 municípios… 3.942 ônibus Euro 6, 203 ônibus elétricos". (A ponte Daux não aparece em **nenhum** dos dois planos — L "ponte" = 0, "BR-101" = 0; não prometer a ponte.) |
| P6 | Artesão/cultura popular (Sâncão) | feira de artesanato + centro histórico | **artesanato 0, artesão 0, feira 0** (F), patrimônio 16 (sentido "patrimônio público"/governança, não contado como cultura), centros históricos 1 (p.41), cultura 6, mestres 0, culturas populares 0, economia criativa 0 (F); incentivo 7 | **B** p.41 ("a preservação do nosso patrimônio histórico, dos centros históricos às obras e acervos que contam quem somos, hoje deteriorados por falta de cuidado"; "aperfeiçoaremos as leis de incentivo"; "distinção entre cultura e entretenimento comercial") + **D** (artesanato, artesão, feira) | **A/B** p.41: "mestras e mestres das culturas populares e tradicionais terão políticas de salvaguarda e valorização, com regras claras de direito autoral sobre os saberes que eles mantêm vivos" + "recuperamos o Cultura Viva e chegamos a 16 mil Pontos e Pontões de Cultura"; **A** p.42: "ampliando o acesso a crédito para iniciativas de economia criativa" |
| P7 | Turismo/gastronomia (Sâncão) | pousada/restaurante + roteiros | **pousada 0, restaurante 0, gastronomia 0, hotel 0** (F), turismo 6 (pp.4, 5, 11, 51, 59, 60), turista 1 (p.60), roteiro 1 (p.60), fungetur 0 (F) | **B** p.59 ("Turismo: uma vocação que rende o que o Brasil tem de sobra e aproveita de menos"; "Toda a infraestrutura que este plano já prevê, dos aeroportos e rodovias às ferrovias, como o Trem do Nordeste, trabalha a favor do turismo") + **D** (pousada, restaurante, gastronomia, hotel) | **A** p.57: "Fungetur apoiou mais de 6 mil operações, mobilizando R$ 2,8 bilhões"; "novos roteiros turísticos baseados em temas como gastronomia, arte, cultura e ecoturismo" |
| P8 | Idoso/aposentado (Sâncão) | INSS + renda do aposentado | idoso 12, aposentado 7, aposentadoria 2 (pp.70, 72), inss 6, renda fixa 1 (p.33) (F) | **B** — programas reais nas pp.33, 37-39, 72-73 (p.33 "o aposentado, que vive de renda fixa e é o primeiro a sentir a alta de preços") → **não é lacuna**; usar como cartão, não como incoerência | pp.19, 22-23, 77 (L) |

\* prefixo (casas "urbaniza…", "endividad…", "assist…").

### Resumo de intenção (por perfil, 1 frase)

- **P1**: o plano F não trata de pesca de forma alguma; o mais próximo é zero.
- **P2**: F promete 2,5 mi de casas (CVA) com "menor taxa de juros possível" e
  regularização fundiária — mas nunca nomeia favela nem periferia como público.
- **P3**: F diagnostica o aperto (dívida do cartão, aposentado, "mesmo salário
  comprando menos") e diz "manter os programas sociais existentes"; não propõe
  nenhum valor novo de salário mínimo nem de transferência.
- **P4**: F fala de indústria só via energia barata e competitividade genérica;
  MEI não aparece.
- **P5**: F diagnostica o "ônibus lotado" e promete metrô/trilhos genéricos; o
  dinheiro quantificado (R$ 900 bi) vai para o eixo Centro-Oeste→portos, não para
  a travessia ilha↔continente.
- **P6**: F valoriza "centros históricos" (que ele mesmo chama de "deteriorados
  por falta de cuidado") via "leis de incentivo"; a economia do artesão não entra.
- **P7**: F trata o turismo como fruto da infraestrutura de aeroportos/ferrovias;
  a pousada e o restaurante locais não entram.
- **P8**: F tem programas reais para o idoso (INSS, fraudes, saúde) — cartão de
  defesa, não de ataque.

## Arquivos da pasta

| arquivo | conteúdo |
|---|---|
| `config.json` / `config_aptos.json` | recorte principal (1210/1880/1228, zona 100) |
| `config_marcolino.json` / `config_marcolino_aptos.json` / `nomes_marcolino.json` | sensibilidade 1589-2018 (Barra do Sambaqui) |
| `conjuntos.json` | `REGIÃO` = 1210+1880+1228 |
| `nomes.json` | nome + zona por local |
| `detalhe_por_secao.csv` | 18 colunas: ano, turno, local, nome, zona, seção, aptos, comparecimento, esquerda, direita, centro, esq3, dir3, branco_nulo, total, margem_esq_pp, esq_sobre_LpR_pct, polarizacao_LpR_sobre_T_pct |
| `detalhe_marcolino.csv` | sensibilidade 2018 (1589) |
| `relatorio.txt` / `relatorio_marcolino.txt` | saída do `05_analise.py` |
| `estrategia-flip-santo-antonio.md` | estratégia 2º turno (7 seções) |
