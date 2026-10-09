# Flip 2º turno — região de Santo Antônio de Lisboa (Sâncão + Sambaqui + Cacupé)

Objetivo: converter, no 2º turno, o voto dado a Flávio no 1º turno, usando
(a) números por seção (`detalhe_por_secao.csv`) e (b) incoerências **verificadas
no texto** do plano dele, com contraponto do plano de Lula — tudo com citação
literal + página (página do txt = página do PDF oficial; ver
`dados/planos/README.md`). Metodologia e cartas-conceito: `README.md` desta pasta.

## 1. O alvo, em números

**REGIÃO** = EBM Paulo Fontes (1210, Sâncão) + NEIM Altino Dealtino Cabral (1880,
Sâncão, só em 2026) + NEI Maria Salomé dos Santos (1228, Sambaqui). Florianópolis,
zona 100.

| eleição | turno | L | R | C | E | N | BN | T | margem | share L |
|---|---|---|---|---|---|---|---|---|---|---|
| 2018 | 1º | 479 | 1.858 | 1.242 | 0 | 0 | 236 | 3.815 | −59,0 pp | 20,5% |
| 2018 | 2º | 1.232 | 2.189 | 0 | 0 | 0 | 358 | 3.779 | −28,0 pp | 36,0% |
| 2022 | 1º | 1.713 | 1.852 | 537 | 0 | 0 | 129 | 4.231 | −3,9 pp | 48,1% |
| 2022 | 2º | 1.891 | 2.185 | 0 | 0 | 0 | 150 | 4.226 | −7,2 pp | 46,4% |
| 2026 | 1º | 1.591 | 1.965 | 421 | 0 | 41 | 132 | 4.150 | −10,5 pp | 44,7% |

C = 3º candidato (2018 Ciro; 2022 Sinval; 2026 = Zema+Renan Santos conforme a
definição da skill — no 1º turno de 2026, "centro" aqui é o 3º colocado, Zema;
`dir3`/`N` = candidatos de direita além do líder). BN = branco + nulo.

**Eleitorado e comparecimento** (aptos por último turno, por conjunto):
2018: 4.428 → 2022: 5.023 → 2026: 5.053 (**+625, +14,1%**). Comparecimento no
1º turno: 86,2% (2018) → 84,2% (2022) → **82,1% (2026)** — 903 abstenções em 2026.

**Por local (último turno de cada ano):**

| local | escola | 2018 2ºT | 2022 2ºT | 2026 1ºT | aptos 2026 |
|---|---|---|---|---|---|
| 1210 | EBM Paulo Fontes (Sâncão) | L 785 × R 1.494 (−31,1 pp; 34,4%) | L 1.171 × R 1.508 (−12,6 pp; 43,7%) | L 924 × R 1.275 (−16,0 pp; 42,0%) | 3.122 |
| 1228 | NEI Maria Salomé dos Santos (Sambaqui) | L 447 × R 695 (−21,7 pp; 39,1%) | **L 720 × R 677 (+3,1 pp; 51,5%)** | **L 621 × R 626 (−0,4 pp; 49,8%)** | 1.770 |
| 1880 | NEIM Altino Dealtino Cabral (Sâncão) | — (outra zona) | — (ausente) | L 46 × R 64 (−16,4 pp; 41,8%) | 161 |

A escola de **Sambaqui (1228) venceu em 2022 e está em empate técnico em 2026**
(−0,4 pp). É o núcleo duro da virada.

**Seções próximas (|margem| ≤ 10 pp) no 1º turno de 2026 — 4 seções, agregado
L 501 × R 501 (empate exato):**

| seção | L | R | margem |
|---|---|---|---|
| 1228/79 | 126 | 134 | −3,1 pp |
| 1210/463 | 128 | 120 | +3,2 pp |
| 1228/78 | 140 | 118 | +8,5 pp |
| 1210/338 | 107 | 129 | −9,3 pp |

**Flips** (mesma local+seção, seções comuns): 2018 2ºT → 2022 2ºT: 3 seções
direita→esquerda (1210/338, 1228/78, 1228/79). 2022 2ºT → 2026 1ºT: 2 seções
esquerda→direita (**1210/338, 1228/79** — as duas viraram de volta para a direita
em 2026; são as seções-alvo nº 1).

**Matemática do 2º turno (2026):** R − L = **374 votos** para virar a região.
Pool disponível (abstenções + branco/nulo) = 903 + 132 = **1.035**. Votos para
virar ≈ 36% do pool — alcançável **sem** exigir migração total: dar as 4 seções
próximas (≈ 200–250 votos de margem agregada) + recuperar as 2 flip (1210/338,
1228/79) + parte do pool. Sanity check: no 2º turno de 2018, neste mesmo
conjunto, o swing 1ºT→2ºT foi **L +753 × R +331** — swing de dois dígitos
aqui já aconteceu.

**Sensibilidade 2018 (Marcolino, Barra do Sambaqui, local 1589 só em 2018):**
L 188 × R 354 no 2º turno (share L 34,7%, 725 aptos) — região pesqueira da
BR-101, historicamente mais à direita; referência para o argumento de pesca
(abaixo), não alvo em 2026 (prédio fechado como local; os eleitores votam nos
locais da região).

## 2. Quem votou no candidato — os perfis da região

1. **Pescador artesanal/camarão** — Sambaqui: portinho, pousos de barco,
   comunidade pesqueira ao redor da NEI Maria Salomé (1228) e da antiga escola
   Marcolino (BR-101, Barra do Sambaqui).
2. **Artesão/cultura popular** — Sâncão: centro histórico, feira de artesanato,
   cerâmica, renda, madeira; base no entorno da EBM Paulo Fontes (1210).
3. **Trabalhador do turismo/gastronomia** — Sâncão: pousadas, restaurantes de
   peixe e bares da Rua do Comércio (1210).
4. **Indústria e comércio do corredor BR-101** — Cacupé: fábricas, madeireiras,
   postos, atacadistas, transportes (sem local próprio; vota em 1210/1228).
5. **Construção civil** — Sambaqui/Cacupé: obras residenciais e industriais do
   corredor (1210/1228).
6. **Autônomo informal/comércio pequeno** — os 3 bairros: mercadinhos,
   ambulantes, serviços (1210/1228).
7. **Morador de baixa renda** — Sambaqui e Cacupé: ruas antigas, encostas,
   demanda por moradia/saneamento (1228).
8. **Aposentado/idoso** — Sâncão: bairro antigo, aposentados e pensionistas
   (1210/1880).
9. **Trabalhador que cruza a ponte** — Cacupé/Sambaqui: quem sai de casa de
   manhã para trabalhar no continente ou volta à tarde (1228/1210).

## 3. As incoerências do plano dele (verificadas no texto, dirigidas ao perfil)

"Não aparece" = contagem 0 em **todas** as variantes da carta (superficiais +
intenção + radicais) no txt inteiro (`dados/planos/flavio.txt`), com fronteira
de palavra. Cartas completas: `README.md`, tabela de cartas-conceito.

### A. Pesca — [Sambaqui: 1228 + memória da Marcolino]

**Lacuna (D):** "pesca" e todas as 10 variantes da carta (pesca, pescador,
pescado, pesqueiro, portinho, camarão, sambaqui, frota, aquicultura,
territórios pesqueiros) — **0 no plano inteiro de Flávio**.
**Contraponto:** Lula p.61: "manteremos nosso compromisso com o fomento à pesca
artesanal e à aquicultura familiar, com a implementação das diretrizes e
prioridades estabelecidas no Plano Nacional da Pesca Artesanal (PNPA).
Fortaleceremos a promoção da proteção dos territórios pesqueiros, da
sociobiodiversidade e dos modos de vida das comunidades das águas".
**Uso:** "O plano para os próximos 4 anos não diz a palavra 'pesca' uma única
vez — nem Sambaqui, nem camarão, nem o portinho. O plano do Lula nomeia o PNPA
e os territórios pesqueiros (página 61)."

### B. Artesão — [Sâncão: 1210]

**Incoerência (C):** Flávio p.41: "a preservação do nosso patrimônio histórico,
dos centros históricos às obras e acervos que contam quem somos, hoje
deteriorados por falta de cuidado" + "aperfeiçoaremos as leis de incentivo" +
"distinção entre cultura e entretenimento comercial" — **×** "artesanato",
"artesão", "feira" = **0 no plano inteiro** (D, 3 variantes). O centro
histórico que ele mesmo chama de "deteriorado" (o Sâncão) não tem política para
a economia que vive nele.
**Contraponto:** Lula p.41: "vamos cuidar de quem guarda esse patrimônio:
mestras e mestres das culturas populares e tradicionais terão políticas de
salvaguarda e valorização, com regras claras de direito autoral sobre os
saberes que eles mantêm vivos" + "recuperamos o Cultura Viva e chegamos a 16 mil
Pontos e Pontões de Cultura"; p.42: "ampliando o acesso a crédito para
iniciativas de economia criativa".
**Uso:** "Ele reconhece que os centros históricos estão 'deteriorados por falta
de cuidado' (página 41) — e depois não diz uma palavra sobre a feira, o
artesanato, o artesão. No plano do Lula, o artesão tem salvaguarda e direito
autoral (página 41)."

### C. Moradia — [Sambaqui/Cacupé: 1228]

**Incoerência (C):** Flávio p.47: "Vamos retomar o Casa Verde e Amarela, com
meta de 2,5 milhões de residências e a menor taxa de juros possível no
financiamento" + "retomar as áreas hoje sob domínio de facções" + "Vamos
promover a urbanização de áreas degradadas, evitando o risco de deslizamentos
em encostas, e incentivar a regularização fundiária" — **×** "favela" = 0,
"periferia" = 0 no plano inteiro (D, 2 variantes). A política existe; o público
não é nomeado.
**Contraponto:** Lula p.45: "Recriamos o Minha Casa Minha Vida – MCMV" +
"2 milhões de moradias com um ano de antecedência, o que nos levou a elevar
esta meta para 3 milhões até o final de 2026. Mais de 80% das obras que estavam
paralisadas já foram retomadas. Um milhão de moradias foram quitadas para
beneficiários do Bolsa Família e BPC"; p.46: "foram R$ 23,3 bilhões para novas
obras de abastecimento de água, esgotamento sanitário e gestão de resíduos
sólidos" + "buscando priorizar periferias historicamente negligenciadas".
**Uso:** "O plano dele promete 2,5 milhões de casas com 'a menor taxa de juros
possível' (página 47) — mas a palavra 'periferia' não aparece uma vez. Para
quem mora em Sambaqui, o plano do Lula é o que nomeia: 80% das obras
paralisadas retomadas e 1 milhão de casas quitadas para famílias do Bolsa
Família (página 45)."

### D. Indústria e MEI — [Cacupé: vota em 1210/1228]

**Lacuna (D) + menção genérica (B):** "MEI" = **0 no plano inteiro** (fronteira
de palavra). As 8 menções a "indústria" de Flávio são genéricas — p.52: "energia
abundante e barata é conta de luz menor e indústria de portas abertas"; p.56:
"indústria, agronegócio, saúde e logística". Nenhuma política para o corredor
industrial de Cacupé nem para o pequeno fornecedor.
**Contraponto:** Lula p.57: "os programas como o Acredita, o Procred 360, o
Desenrola [...] ampliaram as possibilidades de financiamento para esse
segmento. O Pronampe já atingiu 1,6 milhão de operações e o Procred 360 outras
211 mil, mobilizando um montante de R$ 130 bilhões. Criamos a plataforma MEI
Conta Com a Gente".
**Uso:** "Para a fábrica e o lojista de Cacupé, o plano dele tem energia barata
(página 52). 'MEI' não aparece uma vez. O plano do Lula criou a plataforma 'MEI
Conta Com a Gente' e mobilizou R$ 130 bilhões em crédito para quem é pequeno
(página 57)."

### E. Mobilidade ilha↔continente — [Cacupé/Sambaqui: 1228/1210]

**Incoerência (C):** Flávio p.51: "Milhões de brasileiros perdem, todo dia,
horas dentro de um ônibus lotado para ir e voltar do trabalho. É tempo roubado
da família, do descanso e do estudo" + "Vamos pensar o desenvolvimento das
cidades para reduzir o deslocamento da população" — **×** "ponte" = 0 e
"BR-101" = 0 no plano inteiro (D, 2 variantes), e o R$ 900 bilhões quantificado
do mesmo capítulo (p.51) vai para os "corredores de escoamento do Centro-Oeste
até os portos" (Ferrogrão, "trem de cargas que ligará Mato Grosso, o oeste do
Paraná e Santa Catarina", Trem do Nordeste, Transnordestina, Tapajós). O
diagnóstico é a travessia que o morador de Cacupê/Sambaqui faz todos os dias; o
dinheiro vai para outro eixo do país.
**Contraponto:** Lula p.46 (Novo PAC): "resultará em mais 233 km de metrôs,
trens e VLTs e outros 296 km de corredores exclusivos de ônibus no padrão BRT.
Permitirá também renovar a frota de ônibus de 144 municípios, com a aquisição
de 3.942 ônibus Euro 6, 203 ônibus elétricos e 39 veículos sobre trilhos".
(Nota honesta: a ponte Daux não aparece em **nenhum** dos dois planos — "ponte"
e "BR-101" = 0 também em Lula. O contraponto é a frota/corredores, **não** a
ponte — não prometer a ponte.)
**Uso:** "O plano dele diz que 'horas dentro de um ônibus lotado' é 'tempo
roubado' (página 51) — e coloca R$ 900 bilhões no eixo Centro-Oeste→portos
(página 51). A ponte e a BR-101 não aparecem. O plano do Lula (página 46):
296 km de corredores BRT e 203 ônibus elétricos para as cidades."

### F. Salário mínimo — [todos os perfis]

**Lacuna (D):** "salário mínimo" = **0 no plano inteiro** de Flávio. A única
forma plural ("salários mínimos") aparece p.29 no diagnóstico de dívida:
"ganham até três salários mínimos estão endividadas". Ou seja: o plano usa o
salário mínimo para explicar o problema; nunca para resolvê-lo.
**Contraponto:** Lula p.74: "o novo mandato de Lula dará continuidade à política
de valorização do salário mínimo como meio estratégico de distribuição de renda,
combate à pobreza e promoção do desenvolvimento econômico e social".
**Uso:** "O plano dele fala de 'salários mínimos' uma vez — para reclamar que
quem ganha até três está endividado (página 29). Como resolver, não diz. O
plano do Lula continua a 'valorização do salário mínimo' (página 74)."

### G. Transferência de renda — [morador de baixa renda: 1228]

**Lacuna (D):** "bolsa família" = **0**, "bolsa" = **0** no plano de Flávio; as
3 ocorrências de "bolsas" (pp.6, 36, 40) são **bolsas esportivas e de formação
técnica** — nenhuma social. A posição do plano sobre o tema é só manutenção:
p.9 "Manteremos e aperfeiçoaremos os programas sociais"; p.42 "vamos manter os
programas sociais existentes, com aperfeiçoamento da gestão" + "o programa
social é o começo da caminhada, não o fim" ("dependência vira voto. Para nós, o
programa social é ponto de partida").
**Contraponto:** Lula p.12: "O Bolsa Família foi recriado e expandido com
benefícios especiais" + p.58 (Bolsa Família como política de "compra das
famílias") + p.45 (1 mi de casas quitadas para beneficiários do BF/BPC).
**Uso:** "A frase sobre programas sociais do plano dele: 'manter os existentes'
(página 42). 'Bolsa Família' não aparece uma vez. Quem depende dele é o pool do
2º turno aqui: 903 abstenções + 132 brancos/nulos = 1.035 pessoas — a margem
inteira cabe nesse número."

### H. Turismo e gastronomia — [Sâncão: 1210]

**Lacuna (D):** "pousada" = 0, "restaurante" = 0, "gastronomia" = 0, "hotel" = 0
no plano de Flávio. O capítulo de turismo (p.59) depende de outra coisa:
"Turismo: uma vocação que rende o que o Brasil tem de sobra e aproveita de
menos" + "Toda a infraestrutura que este plano já prevê, dos aeroportos e
rodovias às ferrovias, como o Trem do Nordeste, trabalha a favor do turismo".
**Contraponto:** Lula p.57: "Fungetur apoiou mais de 6 mil operações,
mobilizando R$ 2,8 bilhões" + "Buscaremos criar e promover novos roteiros
turísticos baseados em temas como gastronomia, arte, cultura e ecoturismo".
**Uso:** "No plano dele, o turismo depende de aeroporto e Trem do Nordeste
(página 59). A pousada, o restaurante de peixe, a Rua do Comércio: zero. O
plano do Lula (página 57): R$ 2,8 bilhões do Fungetur e roteiros de gastronomia
e ecoturismo."

### (Fora das incoerências: idoso)

O plano de Flávio **tem** programas para o idoso (pp.33, 37-39, 72-73: INSS,
fraudes, saúde; p.33 "o aposentado, que vive de renda fixa e é o primeiro a
sentir a alta de preços") — não é lacuna. Usar como **cartão de defesa**
(seção 4), não de ataque. A alavanca econômica do aposentado daqui é o item F
(salário mínimo/preços).

## 4. Cartões 1-frase por perfil

| perfil | mensagem (1–2 frases, ancorada em página) |
|---|---|
| Pescador (Sambaqui) | "O plano dele não diz 'pesca' nem uma vez; o do Lula nomeia PNPA e territórios pesqueiros (p.61)." |
| Artesão (Sâncão) | "Centros históricos 'deteriorados por falta de cuidado' (p.41 dele) — mas artesão e feira não aparecem; no do Lula, o artesão tem salvaguarda e direito autoral (p.41)." |
| Turismo/gastronomia (Sâncão) | "Turismo dele = aeroporto + Trem do Nordeste (p.59); pousada e restaurante = 0. Do Lula: R$ 2,8 bi Fungetur e roteiros de gastronomia (p.57)." |
| Indústria/MEI (Cacupé) | "Energia barata para a indústria (p.52 dele); 'MEI' não aparece. Do Lula: 'MEI Conta Com a Gente' + R$ 130 bi de crédito (p.57)." |
| Construção (Sambaqui/Cacupé) | "Moradia dele = 2,5 mi de casas com 'menor taxa de juros possível' (p.47), sem nomear periferia; do Lula, 80% das paralisadas retomadas (p.45)." |
| Autônomo informal (3 bairros) | "Plano dele: 'manter os programas sociais existentes' (p.42), sem valor novo; do Lula, 'valorização do salário mínimo' (p.74)." |
| Morador de baixa renda (Sambaqui/Cacupé) | "R$ 23,3 bi de saneamento 'priorizando periferias historicamente negligenciadas' (p.46 do Lula) vs. 'favela'/'periferia' = 0 no plano dele." |
| Aposentado/idoso (Sâncão) | "Defesa: o plano dele tem programas reais para o idoso (pp.37-39, 72-73) — argumentar por preços e salário mínimo (p.74 do Lula), não contra o idoso." |
| Quem cruza a ponte (Cacupê/Sambaqui) | "'Ônibus lotado é tempo roubado' (p.51 dele) — e o R$ 900 bi vai para o Centro-Oeste→portos; do Lula, 296 km BRT + 203 ônibus elétricos (p.46)." |

## 5. O que NÃO dizer

1. **Não atacar o líder pelo nome** porta a porta — atacar "o plano dele". O
   eleitor de 2026 se preserva: "eu votei nele, não no mesmo de antes".
2. **Não entrar no eixo institucional** (segurança, "Brasil sem Medo", facções):
   para o pescador de Sambaqui e o morador de baixa renda de Cacupé, o discurso
   de "áreas sob domínio de facções" (p.47 do plano dele) soa como discurso
   sobre o **bairro dele**. Manter 100% no bolso, na rua, no mercado, na escola.
3. **Não repetir clichê de lado** ("é do povo" × "é dos ricos") — o argumento é
   a incoerência verificada com página, não o rótulo.
4. **Não prometer o que o plano de Lula não diz:** a ponte Daux/BR-101 **não
   aparece em nenhum dos dois planos** (contagem 0 nos dois txts). Prometer a
   ponte é inventar página. O que se promete é frota e corredores (L p.46).
5. **Para os 421 votos de centro do 1º turno (2026):** o argumento é custo de
   vida + não existe alternativa no 2º turno — não o plano de Lula (eles não
   votaram nele).

## 6. Alvo por seção e canal

Prioridade: **flips > próximas > base**, por escola.

**1228 — NEI Maria Salomé dos Santos (Sambaqui)** — a escola que venceu em 2022
e está empatada em 2026 (−0,4 pp). **Todas as 5 seções são alvo.**
- Seções: **79** (−3,1 pp; flip L→R 2026 — alvo nº 1), **78** (+8,5 pp; flip
  R→L 2022, mantido), 80, 353, 455.
- Canais: **portinho e pousos de barco** (pescador, item A), porta da escola e
  ruas do Sambaqui (moradia/saneamento, item C), ponto de ônibus da BR-101
  (item E). Horário: **manhã cedo** (quem desce para pescar) e fim de tarde.

**1210 — EBM Paulo Fontes (Sâncão)** — a maior escola (3.122 aptos, 9 seções).
- Seções: **338** (−9,3 pp; flip L→R 2026 — alvo nº 2), **463** (+3,2 pp),
  depois 76/77/130/208/245/301/391 (base).
- Canais: **Rua do Comércio / feira de artesanato** (artesanato B, turismo H),
  porta da escola (construção C, autônomo F/G), ponto de ônibus (E), salão de
  festas/associação de bairro (idoso — defesa, seção 4). Horário: **tarde**
  (comércio) e sábado (feira).

**1880 — NEIM Altino Dealtino Cabral (Sâncão)** — 1 seção (495), 161 aptos,
−16,4 pp. **Prioridade baixa** (margem larga); ação de porta-a-porta residual
no entorno (idoso/defesa).

**1589 (2018) — Marcolino/Barra do Sambaqui** — só 2018 (prédio saiu do mapa de
locais): **não é alvo em 2026**; serve como argumento (a região pesqueira da
BR-101 era 34,7% em 2018 — a lacuna de pesca, item A, é o motivo do trabalho
de lá ser maior).

**Ordem de trabalho sugerida:** semana 1 = 1228/79 + 1210/338 (as 2 flips) com
argumentos A/C/E; semana 2 = 1228/78 + 1210/463 + B/H na Rua do Comércio;
semana 3 = seções de base + pool (abstenções) com F/G (custo de vida).

## 7. Limites desta análise

- **Renumeração de seções entre anos:** as seções de 2018/2022/2026 não se
  alinham 1:1; "flips" e comparativos por seção usam **apenas as seções comuns**
  (n=12 em 2018×2022; n=14 em 2022×2026). Crescimento/queda por escola são
  robustos (mesmo prédio); por seção, não.
- **2026 tem só 1º turno** — a margem de 2026 é de 1º turno; o 2º turno de 2026
  ainda vai acontecer, e a matemática (374 votos; pool 1.035) é a meta, não
  previsão.
- **2º turno ≠ migração total:** o swing 2018 (L +753 × R +331) mostra o que já
  aconteceu aqui, mas parte dele é indeciso, não conversão do base do líder.
- **"Incoerência" é interpretação estratégica** do documento — nunca juízo de
  boa-fé do autor do plano.
- **Geocodificação revisada local por local** (tabela no README): OSM coloca
  Sambaqui e Cacupé como sub-bairros de Santo Antônio de Lisboa; **Cacupé não
  tem local de votação próprio** (limitação declarada); o local 1589 colide
  entre anos (2018 Marcolino/Barra do Sambaqui × 2022-26 Saco dos Limões) — por
  isso a rodada de sensibilidade separada.
- **Números:** TSE oficial (`detalhe_por_secao` + `votacao_secao`, arquivos
  `_BR`), validação 71/71 de T == comparecimento; planos: txt extraído dos PDFs
  oficiais (sha256 em `dados/planos/README.md`), busca **somente no txt**.
