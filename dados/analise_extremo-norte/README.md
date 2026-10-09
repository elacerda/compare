# Análise — extremo norte de Florianópolis (Canasvieiras + Vargens + Cachoeira do Bom Jesus + Ponta das Canas)

Análise de seções eleitorais (Presidente) de **Florianópolis/SC, zona 100**, para os
locais de votação da **região do extremo norte da ilha**: bairros
**Canasvieiras + Vargem Grande + Vargem Pequena + Vargem dos Ingleses +
Cachoeira do Bom Jesus + Ponta das Canas**. Eleições 2018 (2 turnos), 2022
(2 turnos) e 2026 (1º turno). Estrutura de vira-voto Flávio → Lula:
ver `estrategia-flip-extremo-norte.md`.

Data da análise: 2026-10-09. Fontes: TSE (arquivos `_BR` federais) + planos de
governo em `dados/planos/` (txt extraído; sha256 no `dados/planos/README.md`).
Skill: `flip-flavio-lula` (versão instalada em `~/.codex/skills/`).

## Escopo e locais

### Fato geográfico (OSM)

No OpenStreetMap, **"Canasvieiras" é um bairro guarda-chuva** que inclui, na
cadeia de endereços, Jurerê, Jurerê Leste/Oeste, Daniela, Praia do Forte e as
Vargens. Para esta análise, **Jurerê e Daniela são bairros distintos e fora da
região pedida** (o usuário listou Canasvieiras, Vargens, Cachoeira do Bom Jesus
e Ponta das Canas — sem Jurerê). Os sub-bairros confirmados no OSM dentro da
região: **Vargem Grande > Cachoeira do Bom Jesus**, **Vargem do Bom Jesus >
Cachoeira do Bom Jesus**, **Cachoeira do Bom Jesus Leste**, **Praia do Forte >
Canasvieiras** e **Canasvieiras** (corpo).

### Locais de votação incluídos (NÚCLEO — 8)

| local | nome | endereço (TSE) | bairro (revisão) | anos | observação |
|---|---|---|---|---|---|
| 1260 | EBM Albertina Madalena Dias | Rua Cristóvão Machado de Campos, 1537 | Vargem Grande (OSM; POI direto: "Estrada Cristóvão Machado de Campos, Vargem Grande, Cachoeira do Bom Jesus, CEP 88052") | 2018/2022/2026 | 5 seções em 2026; 1.933 aptos |
| 1279 | EBM Luiz Cândido da Luz (Ponta do Morro) | Rod. SC-403 (Armando Calil Bulos), km 3 | Vargem do Bom Jesus (OSM; POI direto confirma, CEP 88056) | 2018/2022/2026 | 11 seções; 3.858 aptos |
| 1295 | Creche Maria Terezinha Sardá (antigo NEI Praia do Forte) | Rua José Cardoso de Oliveira, 3547 | Canasvieiras (OSM: Praia do Forte > Canasvieiras; o nome da escola confirma "Praia do Forte") | 2018/2022/2026 | 4 seções; 1.314 aptos |
| 1325 | EBM Intendente Aricomedes da Silva | Rod. Leonel Pereira (Nelito), 930 | Cachoeira do Bom Jesus Leste (OSM) | 2018/2022/2026 | 15 seções; **5.643 aptos — a maior escola** |
| 1597 | Escola Dinâmica | Rua Cristóvão Machado de Campos, 1001 | Vargem Grande (OSM) | 2018/2022/2026 | **escola particular** (bilingual) — eleitorado de famílias de maior renda |
| 1708 | E.E.M. Jacó Anderle | Rua Francisco Fausto Martins, s/n | Vargem Grande (OSM) | 2018/2022/2026 | **escola-swing**: −0,9 pp em 2022, −4,5 pp em 2026 |
| 1724 | EBM Virgílio Reis Várzea | Rua Manoel Mancellos Moura, s/n→100 | Canasvieiras (OSM) | 2018/2022/2026 | 11 seções; 4.351 aptos |
| 1856 | NEIM Vila União | Estrada Anarolina Silveira Santos (Rua Ramos, quadra E) | Vargem do Bom Jesus (OSM) | **2026** | local novo (ausente 2018/2022); 177 aptos |

**Não há conjunto de sensibilidade**: as únicas escolas fronteira do recorte
(escolas do corredor Rod. Virgílio Várzea) foram resolvidas para bairros fora
da região (abaixo) e excluídas, não realocadas.

### Excluídos (revisão manual, zona 100 — 64 candidatos, `folha_revisao.tsv`)

| local | por quê |
|---|---|
| **1473 EBM Donícia Maria da Costa** (Rod. Virgílio Várzea, s/n); **1872/1902 NEIM Barreira do Janga** (km 2507, 2026) | **Saco Grande Leste, CEP 88032**: POI com número "Escola Municipal Donícia Maria da Costa, 2507, Rodovia Virgílio Várzea, Saco Grande Leste" é decisivo; o tier por nome sem número casou com o segmento "Canasvieiras" da MESMA rodovia. 1872/1902 = escola desdobrada do mesmo prédio (km 2507) |
| **1627 Creche/NEIM Orlandina Cordeiro** (Rod. Virgílio Várzea, km 380) | **Monte Verde/Saco Grande** (query com o km 380 casou "Monte Verde > Saco Grande" em 2018/22; o hit "Canasvieiras" de 2026 é o segmento sem número da mesma rodovia). Monte Verde não está na região pedida |
| 1538 Creche "Vargem Pequena"/NEIM Vicentina (Rod. Daux, km 16019) | **Ratones** — "Vargem Pequena" é o **nome da creche**, não o bairro |
| 1244 (3 endereços); 1252 (2) | Ratones (OSM: Canto da Cachoeira > Ratones) |
| 1090; 1155; 1481; 1740; 1848 (2); 1910 | Trindade/Itacorubi/Santa Mônica |
| 1163 (2); 1171; 1180; 1864 | Saco Grande/Monte Verde/João Paulo |
| 1201 | Saco Grande Oeste (POI "Hotel Sesc Cacupé") |
| 1457 | Saco Grande Leste |
| 1287; 1309 (3); 1317; 1465; 1660; 1776 | Jurerê/Jurerê Leste/Oeste/Daniela (fora da região pedida) |
| 1210; 1228; 1589 (2); 1880 | Sâncão/Sambaqui (região `dados/analise_santo-antonio/`) |
| 1368; 1376; 1384; 1503; 1562; 1600; 1643; 1678 (2); 1686 (2); 1732; 1830; 1929 | Rio Vermelho/Ingleses (região `dados/analise_norte_floripa/`) |
| 1341 (2) | sem resultado; revisão anterior (santo-antonio): continente |
| 1899 | Rio Tavares > Campeche |

### Limitações declaradas (bairros sem local)

- **Ponta das Canas**: nenhum local de votação identificado na zona 100 —
  limitação (eleitores votam nas escolas vizinhas incluídas).
- **Vargem Pequena**: nenhum local com esse bairro no OSM; a escola **nomada**
  "Creche Vargem Pequena" (1538) está em Ratones — limitação.
- **Vargem dos Ingleses**: nenhum local com esse nome no OSM; o local 1325
  geocodificado em "Cachoeira do Bom Jesus **Leste**" (extremitade voltada a
  Ingleses) é o correspondente mais próximo — incluído.

### Metodologia do geocode (revisão local por local)

1. `01_locais.py` (skill) listou os 41/42/47 locais da zona 100 em
   2018/2022/2026 → 65 pares únicos (local, nome, endereço).
2. `02_geocode.py` (skill, 2–3 tiers: nome da escola → rua+número → rua) sobre os
   65 pares (~1 req/s Nominatim).
3. Revisão manual de cada local: cadeia OSM entre a rua e "Florianópolis",
   query direta de POI para os ambíguos, **ancoragem por número de quilômetro**
   (rodovias longas como a Virgílio Várzea têm segmentos rotulados com bairros
   diferentes — só o hit com o km resolve a ambiguidade; foi assim que 1473/
   1872/1902 foram resolvidas para Saco Grande Leste e 1627 para Monte Verde).
4. Registro completo: `folha_revisao.tsv` (64 linhas: local, nome, endereço,
   bairro OSM, decisão, motivo).

## Dados e decomposição

- `detalhe_por_secao.csv` (18 colunas): saída do `05_analise.py`
  (extração `03_votos.py` + `04_aptos.py`, skill instalada).
- Classificação dos "outros": **C** = centro (3º candidato), **E** = 3º esquerda
  (Boulos 2022), **N** = 3º direita (Zema 2026), **BN** = branco+nulo. Ordem:
  L → R → BN → E → N → C (resto). Convenção: `references/tse-data.md` da skill.

### Validação

- `T` (soma de votos por seção) == `QT_COMPARECIMENTO` do
  `detalhe_votacao_secao_<ANO>_BR.csv` (SC/FLORIANÓPOLIS/zona 100/8 locais/cargo
  Presidente): **253/253 linhas OK** (2018: 108, 2022: 118, 2026: 27) e
  `aptos >= T` em todas.
- Revisão geográfica local por local: `folha_revisao.tsv` (64 candidatos,
  8 locais incluídos, 0 pendentes).

## Cartas-conceito (mineração dos planos)

Regra: busca **somente nos txt** de `dados/planos/` (marcador `=== PAGINA N ===`
= página do PDF). Contagens com **fronteira de palavra** (e plurais).
Classificação A (cobertura explícita c/ valor) / B (menção genérica) / C
(incoerência interna) / D (lacuna: 0 em todas as variantes). Re-verificadas
nesta execução (2026-10-09) para o perfil do território.

| # | Perfil | Necessidade | Variantes verificadas (contagem F / L) | Classe F | Contraponto L |
|---|---|---|---|---|---|
| P1 | Pescador (Canasvieiras/Vargem do Bom Jesus) | pesca artesanal | pesca, pescador, pescado, pesqueiro, portinho, camarão, sambaqui, aquicultura, territórios pesqueiros — **F 0 em todas** | **D** (9 variantes) | **A** p.61: "fomento à pesca artesanal e à aquicultura familiar… Plano Nacional da Pesca Artesanal (PNPA)… proteção dos territórios pesqueiros, da sociobiodiversidade e dos modos de vida das comunidades das águas" |
| P2 | Moradia (Vargens) | casa própria + regularização + saneamento | moradia 2, habitação 2, casa própria 6, minha casa 0, casa verde e amarela 1, **favela 0, periferia 0** (F); encosta 0, escritura 3, fundiária 2 (F) | **A/B** p.47 (CVA "2,5 milhões de residências e a menor taxa de juros possível"; "áreas hoje sob domínio de facções"; "urbanização de áreas degradadas, evitando o risco de deslizamentos em encostas, e incentivar a regularização fundiária") + **D** (favela, periferia) | **A** p.45 (MCMV: "2 milhões de moradias com um ano de antecedência… elevar esta meta para 3 milhões… Mais de 80% das obras que estavam paralisadas já foram retomadas. Um milhão de moradias foram quitadas para beneficiários do Bolsa Família e BPC") + **A** p.46 ("R$ 23,3 bilhões para novas obras de abastecimento de água, esgotamento sanitário… buscando priorizar periferias historicamente negligenciadas") |
| P3 | Salário/custo de vida (todos) | salário mínimo + poder de compra | **salário mínimo 0** (F), "salários mínimos" 1 (p.29, diagnóstico de dívida), cesta básica 0, rotativo 1 (p.32) | **D** (salário mínimo) + **B** (diagnóstico) | p.74: "dará continuidade à política de valorização do salário mínimo como meio estratégico de distribuição de renda, combate à pobreza" |
| P4 | Transferência de renda (baixa renda) | Bolsa Família | **bolsa família 0, bolsa 0** (F; "bolsas" 3× = esportes/formação: pp.6, 36, 40), programa(s) social(is) 3+3 (pp.9, 33, 42, 43, 54) | **D** + **B** (p.9 "Manteremos e aperfeiçoaremos os programas sociais"; p.42 "manter os programas sociais existentes… o programa social é o começo da caminhada, não o fim") | p.12: "O Bolsa Família foi recriado e expandido com benefícios especiais" (4 menções: pp.12, 24, 45, 58) |
| P5 | Mobilidade (corredor Rod. Virgílio Várzea) | ônibus + corredor norte | ônibus 2 (pp.21, 51), mobilidade 5, trânsito 2, deslocamento 1, trilhos 2, metrô 1, **rodovia 0 / rodovias 2** (pp.51, 59) (F) | **B** p.51 ("Milhões de brasileiros perdem, todo dia, horas dentro de um ônibus lotado… tempo roubado"; "reduzir o deslocamento da população"; "linhas de metrô, transporte sobre trilhos e ônibus movidos a eletricidade e biocombustíveis") + **A** p.51 (R$ 900 bi em "rodovias, hidrovias, portos, aeroportos e ferrovias… corredores de escoamento do Centro-Oeste até os portos", Ferrogrão, Trem do Nordeste, Tapajós — eixo nacional, não metropolitano) | **A** p.46 (Novo PAC): "mais 233 km de metrôs, trens e VLTs e outros 296 km de corredores exclusivos de ônibus no padrão BRT… renovar a frota de ônibus de 144 municípios… 3.942 ônibus Euro 6, 203 ônibus elétricos e 39 veículos sobre trilhos" |
| P6 | Turismo/gastronomia (Canasvieiras) | pousada/hotel/restaurante + roteiros | **pousada 0, restaurante 0, gastronomia 0, hotel 0** (F); turismo 6 (pp.4, 5, 11, 51, 59, 60), turista 1 (p.60), roteiro 1 (p.60) (F) | **B** p.59 ("Turismo: uma vocação que rende o que o Brasil tem de sobra e aproveita de menos"; "Toda a infraestrutura que este plano já prevê, dos aeroportos e rodovias às ferrovias, como o Trem do Nordeste, trabalha a favor do turismo") + **D** (pousada, restaurante, gastronomia, hotel) | **A** p.57: "Fungetur apoiou mais de 6 mil operações, mobilizando R$ 2,8 bilhões"; "novos roteiros turísticos baseados em temas como gastronomia, arte, cultura e ecoturismo" |
| P7 | Idoso/aposentado (Canasvieiras) | INSS + renda do aposentado | idoso 5 (pp.23, 34, 37-39), aposentado 4 (pp.26, 33, 72, 73), aposentadoria 2 (pp.70, 72), inss 6, renda fixa 1 (p.33) (F) | **B** — programas reais (p.33 "o aposentado, que vive de renda fixa e é o primeiro a sentir a alta de preços"; pp.37-39, 72-73) → **não é lacuna**; cartão de defesa | pp.22, 77 (L) |

### Resumo de intenção (por perfil, 1 frase)

- **P1**: o plano F não trata de pesca de forma alguma; o mais próximo é zero.
- **P2**: F promete 2,5 mi de casas (CVA) com "menor taxa de juros possível" e
  regularização fundiária — mas nunca nomeia favela nem periferia como público.
- **P3**: F diagnostica o aperto (dívida do rotativo, aposentado) e não propõe
  nenhum valor novo de salário mínimo.
- **P4**: a posição de F sobre transferências é só manutenção: "manter os
  programas sociais existentes" (p.42); "Bolsa Família" não aparece.
- **P5**: F diagnostica o "ônibus lotado" e promete trilhos/ônibus elétricos
  genéricos; o dinheiro quantificado (R$ 900 bi) vai para o eixo
  Centro-Oeste→portos, não para o corredor metropolitano do extremo norte.
- **P6**: F trata o turismo como fruto de aeroportos/ferrovias (Trem do
  Nordeste); a pousada, o hotel e o restaurante de Canasvieiras não entram.
- **P7**: F tem programas reais para o idoso — cartão de defesa, não de ataque.

## Arquivos da pasta

| arquivo | conteúdo |
|---|---|
| `config.json` / `config_aptos.json` | recorte (8 locais, zona 100, 3 arquivos por ano) |
| `conjuntos.json` | `REGIÃO` = 1260+1279+1295+1325+1597+1708+1724+1856 |
| `nomes.json` | nome + zona por local |
| `detalhe_por_secao.csv` | 18 colunas: ano, turno, local, nome, zona, seção, aptos, comparecimento, esquerda, direita, centro, esq3, dir3, branco_nulo, total, margem_esq_pp, esq_sobre_LpR_pct, polarizacao_LpR_sobre_T_pct |
| `folha_revisao.tsv` | revisão geográfica local por local (64 candidatos) |
| `estrategia-flip-extremo-norte.md` | estratégia 2º turno (7 seções) |
