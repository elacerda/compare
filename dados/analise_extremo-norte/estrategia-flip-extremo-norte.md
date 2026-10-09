# Flip 2º turno — extremo norte de Florianópolis (Canasvieiras + Vargens + Cachoeira do Bom Jesus + Ponta das Canas)

Objetivo: converter, no 2º turno, o voto dado a Flávio no 1º turno, usando
(a) números por seção (`detalhe_por_secao.csv`) e (b) incoerências
**verificadas no texto** do plano dele, com contraponto do plano de Lula —
tudo com citação literal + página (página do txt = página do PDF oficial;
ver `dados/planos/README.md`). Metodologia e cartas-conceito: `README.md`
desta pasta.

## 1. O alvo, em números

**REGIÃO** = 8 locais da zona 100: EBM Albertina Madalena (1260, Vargem
Grande), EBM Luiz Cândido da Luz/Ponta do Morro (1279, Vargem do Bom Jesus),
Creche Maria Terezinha Sardá/Praia do Forte (1295, Canasvieiras), EBM
Intendente Aricomedes da Silva (1325, Cachoeira do Bom Jesus Leste), Escola
Dinâmica (1597, Vargem Grande, particular), E.E.M. Jacó Anderle (1708, Vargem
Grande), EBM Virgílio Reis Várzea (1724, Canasvieiras), NEIM Vila União (1856,
Vargem do Bom Jesus, só 2026).

| eleição | turno | L | R | C | E | N | BN | T | margem | share L |
|---|---|---|---|---|---|---|---|---|---|---|
| 2018 | 1º | 1.679 | 6.741 | 3.263 | 0 | 0 | 1.048 | 12.731 | −60,1 pp | 19,9% |
| 2018 | 2º | 3.784 | 7.789 | 0 | 0 | 0 | 1.097 | 12.670 | −34,6 pp | 32,7% |
| 2022 | 1º | 6.071 | 7.546 | 1.559 | 0 | 0 | 625 | 15.801 | −10,8 pp | 44,6% |
| 2022 | 2º | 6.528 | 8.575 | 0 | 0 | 0 | 626 | 15.729 | −13,6 pp | 43,2% |
| 2026 | 1º | 5.968 | 8.648 | 1.480 | 0 | 80 | 638 | 16.814 | −18,3 pp | 40,8% |

C = 3º candidato (2018 Ciro; 2022 Sinval; 2026 = 3º lugar); N = 3º de direita
(Zema 2026); BN = branco + nulo.

**Eleitorado e comparecimento:** 15.797 (2018) → 19.769 (2022) → **21.882
(2026): +6.085 aptos (+38,5%)** — o crescimento mais forte entre as análises
da ilha (boom de construção do extremo norte). Comparecimento caindo:
80,2% → 79,6% → **76,8%** (5.068 abstenções em 2026).

**Por local (share L no último turno de cada ano + 2026 1ºT):**

| local | escola (bairro) | 2018 2ºT | 2022 2ºT | 2026 1ºT | aptos 2026 |
|---|---|---|---|---|---|
| 1708 | Jacó Anderle (Vargem Grande) | 39,5% | **49,5% (−0,9 pp)** | **47,7% (−4,5 pp)** | 3.063 |
| 1856 | NEIM Vila União (Vargem do Bom Jesus) | — | — | 46,0% (−8,0 pp) | 177 |
| 1597 | Escola Dinâmica (Vargem Grande, part.) | 35,2% | 43,9% | 41,5% (−17,0 pp) | 1.543 |
| 1325 | Intendente Aricomedes (Cachoeira Leste) | 31,6% | 42,4% | 40,5% (−19,1 pp) | **5.643** |
| 1724 | Virgílio Reis Várzea (Canasvieiras) | 30,9% | 42,7% | 40,3% (−19,4 pp) | 4.351 |
| 1260 | Albertina Madalena (Vargem Grande) | 30,0% | 40,5% | 39,6% (−20,8 pp) | 1.933 |
| 1279 | Luiz Cândido/Ponta do Morro (Vargem do Bom Jesus) | 33,0% | 43,0% | 39,1% (−21,7 pp) | 3.858 |
| 1295 | Creche Sardá/Praia do Forte (Canasvieiras) | 35,8% | 41,2% | **35,0% (−30,1 pp)** | 1.314 |

**1708 (Jacó Anderle) é a escola-swing**: empatada em 2022 (−0,9 pp) e em
desvantagem mínima em 2026 (−4,5 pp). **1295 (Praia do Forte) é a mais à
direita** (−30,1 pp).

**Seções próximas (|margem| ≤ 10 pp) no 1º turno de 2026 — 12 seções, agregado
L 1.335 × R 1.420 (−3,1 pp):**

| seção | L | R | margem |
|---|---|---|---|
| 1708/461 | 115 | 117 | −0,9 pp |
| 1708/512 | 112 | 114 | −0,9 pp |
| 1325/473 | 105 | 110 | −2,3 pp |
| 1708/483 | 100 | 108 | −3,8 pp |
| 1708/377 | 119 | 135 | −6,3 pp |
| 1279/519 | 123 | 141 | −6,8 pp |
| 1708/427 | 124 | 106 | +7,8 pp |
| 1856/496 | 46 | 54 | −8,0 pp |
| 1708/357 | 119 | 141 | −8,5 pp |
| 1708/401 | 110 | 132 | −9,1 pp |
| 1325/445 | 143 | 119 | +9,2 pp |
| 1724/404 | 119 | 143 | −9,2 pp |

**7 das 12** estão em 1708 (Vargem Grande).

**Flips** (seções comuns): 2018 2ºT → 2022 2ºT (n=45): 1 direita→esquerda
(1724/404). 2022 2ºT → 2026 1ºT (n=52): 3 esquerda→direita (**1279/474,
1708/461, 1724/404**). **1724/404 é vereadora de ida e volta** (virou p/ L em
2022, voltou p/ R em 2026).

**Matemática do 2º turno (2026):** R − L = **2.680 votos** para virar a
região inteira. Pool (abstenções + BN) = 5.068 + 638 = **5.706**. Virar a
região inteira exigiria ≈ 17 pp de swing — **fora de alcance** (regra da
skill: > ~15 pp → declarar e decompor). O swing 1ºT→2ºT de 2018 aqui foi
**L +2.105 × R +1.048** (45 seções nos dois turnos) — dois dígitos já
aconteceram neste território.

**Meta realista (decomposta):**
1. **Virar 1708 (Jacó Anderle)**: L 903 × R 989 → **43 votos** (7 seções
   próximas + a flip 461).
2. **Virar 1856 (Vila União)**: **4 votos** (seção 496, −8,0 pp, 177 aptos).
3. **Seções próximas restantes**: 1325/473, 1279/519, 1724/404 (recuperar a
   flip de 2022) + segurar 1708/427 e 1325/445 (≈ 100–150 votos de margem).
4. **Recuperar as flips de 2026**: 1279/474 e 1708/461 (≈ 30–60 votos).
5. **Pool**: 7–10% dos 5.706 (≈ 400–600 votos) via custo de vida +
   comparecimento.
Total: **≈ 600–900 votos** — suficiente para virar as 2 escolas-swing,
capturar a maioria das seções próximas e reduzir a margem regional de −2.680
para ≈ −1.800.

## 2. Quem votou no candidato — os perfis da região

1. **Pescador artesanal** — Canasvieiras (portinho, camarão, frota pequena) e
   Vargem do Bom Jesus (1279, 1856; comunidade pesqueira da SC-403).
2. **Trabalhador do turismo/gastronomia/lodging** — orla de Canasvieiras e
   Praia do Forte (1295, 1724): resorts, hotéis, pousadas, restaurantes.
3. **Construção civil** — o boom que dobrou o eleitorado em 8 anos
   (+38,5%): Canasvieiras e Vargens (1260, 1325, 1708, 1724).
4. **Morador de baixa renda** — as Vargens: Vargem Grande (1260, 1708),
   Vargem do Bom Jesus (1279, 1856), encostas e loteamentos antigos.
5. **Autônomo informal/comércio pequeno** — orla e shopping de Canasvieiras
   (1295, 1724) e mercados das Vargens (1260, 1325, 1708).
6. **Trabalhador do corredor** — quem pega ônibus pela Rod. Virgílio Várzea
   / SC-403 para Ingleses e o centro (todos os locais, manhã e fim de tarde).
7. **Aposentado/idoso** — Canasvieiras, bairro antigo (1295, 1724).
8. **Famílias de escola particular** — 1597 (Escola Dinâmica, bilingual):
   perfil de renda acima da média do recorte — tratar à parte (ver "o que não
   dizer").

## 3. As incoerências do plano dele (verificadas no texto, dirigidas ao perfil)

"Não aparece" = contagem 0 em **todas** as variantes da carta (superficiais +
intenção + radicais + plurais, fronteira de palavra) no txt inteiro
(`dados/planos/flavio.txt`). Cartas completas: `README.md`.

### A. Pesca — [1279, 1856, Canasvieiras]

**Lacuna (D):** "pesca" e as 9 variantes da carta (pesca, pescador, pescado,
pesqueiro, portinho, camarão, sambaqui, aquicultura, territórios pesqueiros) —
**0 no plano inteiro de Flávio**.
**Contraponto:** Lula p.61: "manteremos nosso compromisso com o fomento à
pesca artesanal e à aquicultura familiar, com a implementação das diretrizes e
prioridades estabelecidas no Plano Nacional da Pesca Artesanal (PNPA).
Fortaleceremos a promoção da proteção dos territórios pesqueiros, da
sociobiodiversidade e dos modos de vida das comunidades das águas".
**Uso:** "O plano para os próximos 4 anos não diz a palavra 'pesca' uma única
vez — nem Canasvieiras, nem camarão, nem o portinho. O plano do Lula nomeia o
PNPA e os territórios pesqueiros (página 61)."

### B. Moradia — [Vargens: 1260, 1279, 1597, 1708, 1856, 1325]

**Incoerência (C):** Flávio p.47: "Vamos retomar o Casa Verde e Amarela, com
meta de 2,5 milhões de residências e a menor taxa de juros possível no
financiamento" + "retomar as áreas hoje sob domínio de facções" + "Vamos
promover a urbanização de áreas degradadas, evitando o risco de deslizamentos
em encostas, e incentivar a regularização fundiária" — **×** "favela" = 0,
"periferia" = 0 no plano inteiro (D, 2 variantes). A política existe; o
público das Vargens não é nomeado.
**Contraponto:** Lula p.45: "Recriamos o Minha Casa Minha Vida – MCMV" +
"2 milhões de moradias com um ano de antecedência, o que nos levou a elevar
esta meta para 3 milhões até o final de 2026. Mais de 80% das obras que
estavam paralisadas já foram retomadas. Um milhão de moradias foram quitadas
para beneficiários do Bolsa Família e BPC"; p.46: "foram R$ 23,3 bilhões para
novas obras de abastecimento de água, esgotamento sanitário e gestão de
resíduos sólidos" + "buscando priorizar periferias historicamente
negligenciadas".
**Uso:** "O plano dele promete 2,5 milhões de casas com 'a menor taxa de
juros possível' (página 47) — mas 'periferia' e 'favela' não aparecem uma vez.
Quem mora em Vargem Grande ou Vargem do Bom Jesus: o plano do Lula é o que
nomeia o público — 80% das obras paralisadas retomadas e 1 milhão de casas
quitadas para famílias do Bolsa Família (página 45)."

### C. Salário mínimo — [todos os perfis]

**Lacuna (D):** "salário mínimo" = **0 no plano inteiro** de Flávio. A única
forma plural ("salários mínimos") aparece p.29 no diagnóstico de dívida:
"ganham até três salários mínimos estão endividadas". O plano usa o salário
mínimo para explicar o problema; nunca para resolvê-lo.
**Contraponto:** Lula p.74: "o novo mandato de Lula dará continuidade à
política de valorização do salário mínimo como meio estratégico de
distribuição de renda, combate à pobreza e promoção do desenvolvimento
econômico e social".
**Uso:** "O plano dele fala de 'salários mínimos' uma vez — para reclamar que
quem ganha até três está endividado (página 29). Como resolver, não diz. O
plano do Lula continua a 'valorização do salário mínimo' (página 74)."

### D. Transferência de renda — [baixa renda: 1260, 1279, 1708, 1856, 1325]

**Lacuna (D):** "bolsa família" = **0**, "bolsa" = **0** no plano de Flávio
(as 3 ocorrências de "bolsas" — pp.6, 36, 40 — são **bolsas esportivas e de
formação técnica**, nenhuma social). A posição do plano é só manutenção:
p.9 "Manteremos e aperfeiçoaremos os programas sociais"; p.42 "vamos manter
os programas sociais existentes, com aperfeiçoamento da gestão" + "o
programa social é o começo da caminhada, não o fim" ("dependência vira voto.
Para nós, o programa social é ponto de partida").
**Contraponto:** Lula p.12: "O Bolsa Família foi recriado e expandido com
benefícios especiais" (o programa aparece 4×: pp.12, 24, 45, 58).
**Uso:** "A frase sobre programas sociais do plano dele: 'manter os
existentes' (página 42). 'Bolsa Família' não aparece uma vez. O pool do 2º
turno aqui é de 5.706 pessoas (abstenções + brancos/nulos) — a margem inteira
dessa região cabe nesse número."

### E. Mobilidade do corredor — [todos: Rod. Virgílio Várzea/SC-403]

**Incoerência (C):** Flávio p.51: "Milhões de brasileiros perdem, todo dia,
horas dentro de um ônibus lotado para ir e voltar do trabalho. É tempo roubado
da família, do descanso e do estudo" + "Vamos pensar o desenvolvimento das
cidades para reduzir o deslocamento da população, com o transporte coletivo
como base" — **×** o R$ 900 bilhões quantificado no mesmo capítulo (p.51) vai
para "rodovias, hidrovias, portos, aeroportos e ferrovias… os corredores de
escoamento do Centro-Oeste até os portos" (Ferrogrão, Trem do Nordeste,
Tapajós — eixo nacional de logística), e a única outra menção a rodovias
(p.59) é no capítulo de turismo. O diagnóstico é a viagem que o morador do
extremo norte faz todo dia; o dinheiro vai para outro eixo do país.
**Contraponto:** Lula p.46 (Novo PAC): "resultará em mais 233 km de metrôs,
trens e VLTs e outros 296 km de corredores exclusivos de ônibus no padrão
BRT. Permitirá também renovar a frota de ônibus de 144 municípios, com a
aquisição de 3.942 ônibus Euro 6, 203 ônibus elétricos e 39 veículos sobre
trilhos".
**Uso:** "O plano dele diz que 'horas dentro de um ônibus lotado' é 'tempo
roubado' (página 51) — e coloca R$ 900 bilhões no eixo Centro-Oeste→portos
(página 51). O corredor do extremo norte (Virgílio Várzea) não aparece. O
plano do Lula (página 46): 296 km de corredores BRT e 203 ônibus elétricos
para as cidades."

### F. Turismo e gastronomia — [Canasvieiras: 1295, 1724]

**Lacuna (D):** "pousada" = 0, "restaurante" = 0, "gastronomia" = 0, "hotel" =
0 no plano de Flávio. O capítulo de turismo (p.59) depende de outra coisa:
"Turismo: uma vocação que rende o que o Brasil tem de sobra e aproveita de
menos" + "Toda a infraestrutura que este plano já prevê, dos aeroportos e
rodovias às ferrovias, como o Trem do Nordeste, trabalha a favor do turismo".
**Contraponto:** Lula p.57: "Fungetur apoiou mais de 6 mil operações,
mobilizando R$ 2,8 bilhões" + "Buscaremos criar e promover novos roteiros
turísticos baseados em temas como gastronomia, arte, cultura e ecoturismo".
**Uso:** "No plano dele, o turismo depende de aeroporto e Trem do Nordeste
(página 59). A pousada, o hotel e o restaurante da orla de Canasvieiras:
zero. O plano do Lula (página 57): R$ 2,8 bilhões do Fungetur e roteiros de
gastronomia e ecoturismo."

### (Fora das incoerências: idoso)

O plano de Flávio **tem** programas para o idoso (pp.33, 37-39, 72-73: INSS,
fraudes, saúde; p.33 "o aposentado, que vive de renda fixa é o primeiro a
sentir a alta de preços") — não é lacuna. Usar como **cartão de defesa**
(seção 4); a alavanca econômica do aposentado é o item C (salário mínimo/
preços).

## 4. Cartões 1-frase por perfil

| perfil | mensagem (1–2 frases, ancorada em página) |
|---|---|
| Pescador (Canasvieiras/Vargem do Bom Jesus) | "O plano dele não diz 'pesca' nem uma vez; o do Lula nomeia PNPA e territórios pesqueiros (p.61)." |
| Turismo/lodging (Canasvieiras) | "Turismo dele = aeroporto + Trem do Nordeste (p.59); pousada, hotel e restaurante = 0. Do Lula: R$ 2,8 bi Fungetur e roteiros de gastronomia (p.57)." |
| Construção (Canasvieiras/Vargens) | "Moradia dele = 2,5 mi de casas com 'menor taxa de juros possível' (p.47), sem nomear periferia; do Lula, 80% das paralisadas retomadas (p.45)." |
| Morador de baixa renda (Vargens) | "R$ 23,3 bi de saneamento 'priorizando periferias historicamente negligenciadas' (p.46 do Lula) vs. 'favela'/'periferia' = 0 no plano dele." |
| Autônomo/comércio (orla + Vargens) | "Plano dele: 'manter os programas sociais existentes' (p.42), sem valor novo; do Lula, 'valorização do salário mínimo' (p.74)." |
| Corredor/ônibus (todos) | "'Ônibus lotado é tempo roubado' (p.51 dele) — e o R$ 900 bi vai para o Centro-Oeste→portos; do Lula, 296 km BRT + 203 ônibus elétricos (p.46)." |
| Aposentado/idoso (Canasvieiras) | "Defesa: o plano dele tem programas reais para o idoso (pp.37-39, 72-73) — argumentar por preços e salário mínimo (p.74 do Lula), não contra ele." |
| Famílias de escola particular (1597) | "Custo de vida + crédito: 'manter os existentes' (p.42 dele) sem valor novo × valorização do salário mínimo (p.74 do Lula); não usar o argumento de transferência de renda." |

## 5. O que NÃO dizer

1. **Não atacar o líder pelo nome** porta a porta — atacar "o plano dele". O
   eleitor de 2026 se preserva: "eu votei nele, não no mesmo de antes".
2. **Não entrar no eixo institucional** (segurança, "Brasil sem Medo",
   facções): para os moradores das Vargens, o discurso de "áreas sob domínio
   de facções" (p.47 do plano dele) soa como discurso sobre o **bairro dele**.
   Manter 100% no bolso, na rua, no mercado, na escola, no ponto de ônibus.
3. **Não repetir clichê de lado** ("é do povo" × "é dos ricos") — o argumento
   é a incoerência verificada com página, não o rótulo.
4. **Não prometer o que o plano de Lula não diz:** nenhuma rodovia/bridge
   específica do corredor aparece em nenhum dos dois planos (contagem 0 nos
   dois txts para "BR-101"; a "rodovia" de F é genérica). O contraponto de
   mobilidade é **frota e corredores BRT** (L p.46) — não uma obra específica
   da Virgílio Várzea.
5. **Para os 1.480 votos de centro (C) + 80 de 3º direita (N) do 1º turno
   de 2026:** o argumento é custo de vida + não existe alternativa no 2º
   turno — não o plano de Lula (eles não votaram nele).
6. **Para 1597 (escola particular, renda acima da média):** não usar
   transferências (Bolsa Família) — o perfil não se identifica com isso;
   usar custo de vida, salário mínimo e crédito.

## 6. Alvo por seção e canal

Prioridade: **flips > próximas > base**, por escola.

**1708 — E.E.M. Jacó Anderle (Vargem Grande)** — **a escola-swing** (−0,9 pp
em 2022; −4,5 pp em 2026; 3.063 aptos). **Meta: virar a escola (43 votos).**
- Seções: **461** (−0,9 pp; flip L→R 2026 — alvo nº 1), **512** (−0,9), **483**
  (−3,8), **377** (−6,3), **357** (−8,5), **401** (−9,1); segurar **427**
  (+7,8).
- Canais: porta da escola (manhã), ponto de ônibus do corredor (saída/retorno
  do trabalho), canteiros de obra da Vargem Grande (fim de tarde).
- Argumentos: C (salário mínimo/custo de vida) + D (transf. para a base de
  baixa renda) + E (ônibus).

**1856 — NEIM Vila União (Vargem do Bom Jesus)** — meta: virar (4 votos).
- Seção **496** (−8,0 pp; 177 aptos — escola pequena, efeito de porta a porta
  direto).
- Canais: Rua Ramos/Vila União (tarde), porta da creche (manhã).
- Argumentos: B (moradia/saneamento) + D.

**1325 — EBM Intendente Aricomedes (Cachoeira do Bom Jesus Leste)** — a maior
escola (5.643 aptos); margem −19,1 pp (base) + 2 seções próximas.
- Seções: **473** (−2,3), segurar **445** (+9,2); resto = base.
- Canais: corredor da Leonel Pereira/Nelito (ponto de ônibus, manhã), comércio
  local (tarde).
- Argumentos: D + C + E.

**1279 — EBM Luiz Cândido da Luz/Ponta do Morro (Vargem do Bom Jesus)** —
margem −21,7 pp + 1 seção próxima + 1 flip.
- Seções: **519** (−6,8), recuperar **474** (flip L→R 2026).
- Canais: **corredor da SC-403 e área do portinho** (pescador — argumento A),
  ponto de ônibus (manhã cedo).
- Argumentos: A (pesca) + E.

**1724 — EBM Virgílio Reis Várzea (Canasvieiras)** — margem −19,4 pp + seção
vereadora.
- Seção **404** (−9,2 pp; flip R→L 2022 e L→R 2026 — recuperar).
- Canais: rua da Várzea/orla (tarde e sábado), comércio da Canasvieiras
  (gastronomia/turismo — argumento F para o comércio; C para o morador).
- Argumentos: F (comércio de turismo) + C/D (moradores).

**1260 — Albertina Madalena (Vargem Grande)** — base (−20,8 pp): ação
residual de porta a porta (B/D).

**1295 — Creche Sardá/Praia do Forte (Canasvieiras)** — a mais à direita
(−30,1 pp): **fora do foco realista** (margem larga); ação de presença na
orla (F) sem meta de virada.

**1597 — Escola Dinâmica (Vargem Grande, particular)** — base (−17,0 pp);
canal: porta da escola no horário de **busca** (11h/17h). Argumento: custo
de vida (C) — **não** transferências.

**Ordem de trabalho sugerida:** semana 1 = 1708 (6 seções próximas + flip) +
1856 com C/D/E; semana 2 = 1325/473 + 1279 (519, 474 + portinho/SC-403 com
A) + 1724/404; semana 3 = seções de base + pool (abstenções) com C/D
(custo de vida) + 1597 (busca de escola).

## 7. Limites desta análise

- **Renumeração de seções entre anos:** os comparativos por seção (flips,
  próximas) usam **apenas as seções comuns** (n=45 em 2018×2022; n=52 em
  2022×2026). Por escola são robustos (mesmo prédio); por seção, não.
- **2026 tem só 1º turno** — a margem de 2026 é de 1º turno; a matemática
  (2.680 votos; pool 5.706) é a meta, não previsão.
- **Virar a região inteira é fora de alcance** (≈ 17 pp de swing); a meta
  realista é decomposta (seção 1): 2 escolas-swing + seções próximas +
  parte do pool.
- **2º turno ≠ migração total:** o swing 2018 (L +2.105 × R +1.048) mostra o
  que já aconteceu aqui, mas parte dele é indeciso, não conversão da base do
  líder.
- **"Incoerência" é interpretação estratégica** do documento — nunca juízo de
  boa-fé do autor do plano.
- **Geocodificação revisada local por local** (`folha_revisao.tsv`, 64
  candidatos): no OSM, "Canasvieiras" é bairro guarda-chuva que inclui
  Jurerê/Daniela (excluídos — não fazem parte da região pedida); as escolas
  do corredor Rod. Virgílio Várzea (1473/1627/1872/1902) foram resolvidas
  por **número de quilômetro + POI** para Saco Grande Leste/Monte Verde
  (fora da região); "Creche Vargem Pequena" (1538) é nome de escola, não
  bairro (está em Ratones). **Ponta das Canas e Vargem Pequena não têm local
  de votação próprio** — limitação declarada.
- **Números:** TSE oficial, validação **253/253** de T == comparecimento;
  planos: txt extraído dos PDFs oficiais (sha256 em `dados/planos/README.md`),
  busca **somente no txt**.
