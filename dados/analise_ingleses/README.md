# Ingleses (Florianópolis/SC) — Evolução da polarização eleitoral 2018–2026

Análise dos votos na corrida presidencial (esquerda × direita) nas seções do
bairro **Ingleses**, Florianópolis (SC), para as eleições de **2018**
(Haddad × Bolsonaro), **2022** (Lula × Bolsonaro) e **2026** (Lula × Flávio
Bolsonaro). Metodologia idêntica a `../analise_riverio_v/README.md`.

> **Rerun 2026-10-08 (pipeline v2 da skill `flip-flavio-lula`)**: todos os
> números abaixo reproduzidos exatamente (regressão conferida contra os
> valores antigos); novas seções — "Decomposição de 'Outros'", "Matemática
> do 2º turno", "Validação" e flips no mesmo turno. Correção: "esq (L+R)/T"
> de 2018 1º é **64,5%** (12.170/18.855) — o 69,0% anterior era erro de
> cálculo.

## Metodologia

1. **Zona eleitoral.** Todas as seções de Ingleses estão na **zona 100** de
   Florianópolis (cód. 81051) — verificado que as zonas 12/13 (centro e sul
   da Ilha) não contêm nenhum local de Ingleses.
2. **Identificação do bairro.** O TSE não traz o nome do bairro; os locais de
   votação são escolas identificadas por endereço. Cada escola da zona 100
   (47 locais) foi geocodificada no OSM/Nominatim (2 rodadas, em 07/10/2026)
   e o bairro foi lido do endereço devolvido (suburb/neighbourhood).
3. **Conjunto núcleo (7 locais, confirmados como Ingleses pelo OSM):**
   - `1562` — Colégio Santa Terezinha (Serv. Safira, **Ingleses Centro**), 13 seções
   - `1600` — Centro Educacional Universo (Serv. Prof. Nilson José de Jesus, **Ingleses Centro**), 10 seções
   - `1732` — EBM Herondina Medeiros Zeferino (Serv. Três Marias, **Ingleses Centro**), 25 seções
   - `1376` — NEIM Gentil Mathias da Silva (Estr. Dom João Becker, **Ingleses Sul**), 11 seções
   - `1643` — EBM Maria Tomazia Coelho (Estr. Vereador Onildo Lemos, **Santinho/Ingleses Sul**), 10 seções
   - `1678` — EBM Antônio Paschoal Apóstolo (Rod. João Gualberto Soares, **Capivari**), 9 seções
   - `1686` — Anexo da EEB Intendente José Fernandes (Estr. Dário Manoel Cardoso, **Capivari**), 15 seções
   Total 2026: **93 seções, 34.882 aptos**.
4. **Fronteira (sensibilidade):** `1368` — EEB Intendente José Fernandes
   (Rua João Gualberto Soares, 324), 18 seções. A escola-mãe fica no início da
   rodovia João Gualberto Soares, na divisa Ingleses×Muquém/Rio Vermelho; seu
   anexo (`1686`) está em Capivari/Ingleses. **1368 também aparece no conjunto
   "ext" de `../analise_riverio_v`** — ao somar os dois bairros, contar 1368
   apenas uma vez.
5. **Excluídos (verificados como fora de Ingleses pelo OSM):** 1244/1252/1538
   ("Ratones", localidade rural da Região Norte da Ilha), 1260/1341/1708/1856
   (continente/Cachoeira do Bom Jesus), 1589 (Sambaqui), 1481 (Itacorubi),
   1287 (Jurerê), 1279 (Ponta do Morro), 1210/1880 (Santo Antônio de Lisboa),
   1163/1171/1180/1201/1864/1872/1902 (Saco Grande), 1309/1317/1465/1473/1627/1724
   (Jurerê/Canasvieiras), 1155/1740/1910/1848/1090 (Lagoa/Trindade/Itacorubi),
   1295 (Forte/Jurerê), 1899 (Rio Tavares), 1384 (Rio Vermelho, mesma rua da
   Darcy Ribeiro), 1228 (Sambaqui, baixa confiança).
6. **Convenções.** Mesmas de Rio Vermelho: L = Haddad/Lula; R = Bolsonaro/Flávio;
   margem = (L−R)/(L+R) em pp; polarização = (L+R)/T; O = demais candidatos +
   brancos/nulos, decomposto no pipeline v2 em C (centro), E (3º esq.),
   N (3º dir.) e BN (branco+nulo).
7. **Limitação de vinculação.** Seções casadas entre eleições por
   `NR_LOCAL_VOTACAO` + número de seção quando coincidente; o TSE renumera
   seções a cada eleição (fallback por nome do local; cobertura do match
   2022→2026: 97% por código).

## Resultados — núcleo (7 locais)

| Eleição | Turno | Esquerda (L) | Direita (R) | Outros | Total | esq (L+R)/T | Margem | Share L |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 2018 | 1º | 2.164 | 10.006 | 6.685 | 18.855 | 64,5% | **−64,4 pp** | 17,8% |
| 2018 | 2º | 5.486 | 11.551 | 1.661 | 18.698 | 91,1% | **−35,6 pp** | 32,2% |
| 2022 | 1º | 9.714 | 11.740 | 3.181 | 24.635 | 87,1% | **−9,4 pp** | 45,3% |
| 2022 | 2º | 10.393 | 13.423 | 866 | 24.682 | 96,5% | **−12,7 pp** | 43,6% |
| 2026 | 1º | 9.280 | 13.548 | 3.271 | 26.099 | 87,5% | **−18,7 pp** | 40,7% |

### Sensibilidade — núcleo + fronteira (1368)

| Eleição | Turno | L | R | Outros | Total | esq (L+R)/T | Margem | Share L |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 2018 | 1º | 2.927 | 12.949 | 8.584 | 24.460 | 64,9% | −63,1 pp | 18,4% |
| 2018 | 2º | 7.162 | 14.994 | 2.158 | 24.314 | 91,1% | −35,3 pp | 32,3% |
| 2022 | 1º | 11.605 | 14.329 | 3.826 | 29.760 | 87,1% | −10,5 pp | 44,7% |
| 2022 | 2º | 12.443 | 16.341 | 1.066 | 29.850 | 96,4% | −13,5 pp | 43,2% |
| 2026 | 1º | 10.864 | 16.214 | 3.864 | 30.942 | 87,5% | −19,8 pp | 40,1% |

### Decomposição de "Outros" — 2026 1º turno

| Conjunto | Centro (C) | 3º esq. (E) | 3º dir. (N) | Branco+Nulo (BN) |
|---|---:|---:|---:|---:|
| Núcleo | 2.519 | 0 | 0 | 752 |
| Núcleo + fronteira 1368 | 2.909 | 0 | 0 | 955 |

### Por local (núcleo)

| Local | Bairro | 2018 2ºT (margem) | 2022 2ºT (margem) | 2026 1ºT (L × R, margem) | aptos 2026 |
|---|---|---|---|---|---:|
| 1678 | Capivari | −20,4 pp | **+1,9 pp (E venceu)** | 1.030 × 1.187 (−7,1 pp) | 3.420 |
| 1686 | Capivari | −37,5 pp | −7,3 pp | 1.617 × 2.020 (−11,1 pp) | 5.735 |
| 1732 | Ingleses Centro | −30,7 pp | −6,2 pp | 2.581 × 3.488 (−14,9 pp) | 9.482 |
| 1376 | Ingleses Sul | −36,5 pp | −17,4 pp | 1.088 × 1.640 (−20,2 pp) | 4.060 |
| 1643 | Santinho | −41,0 pp | −17,4 pp | 953 × 1.468 (−21,3 pp) | 3.606 |
| 1562 | Ingleses Centro | −40,6 pp | −23,9 pp | 1.156 × 2.142 (−29,9 pp) | 4.940 |
| 1600 | Ingleses Centro | −38,8 pp | −25,1 pp | 855 × 1.603 (−30,4 pp) | 3.639 |
| 1368 (fronteira) | divisa RV | −34,5 pp | −17,5 pp | 1.584 × 2.666 (−25,5 pp) | — |

## Seções 2026 (núcleo) e "flips"

- 2026 1º turno, núcleo: **3 seções à esquerda** (1643/435 +6,8 pp; 1686/508
  +0,8 pp; 1732/440 +0,4 pp), **2 empatadas** (1678/355, 1686/447) e 88 à direita.
- **22 seções com |margem| ≤ 10 pp** (a "zona conversível"): L = 2.561 ×
  R = 2.760 (margem agregada −3,7 pp; ±1σ ≈ 6 pp por seção). Distribuição:
  1678×6, 1686×7, 1732×7, 1376×1, 1643×1. Se a zona virasse 55×45, ganho
  ≈ **+365 votos** (agregado atual da zona: 48,1 × 51,9).
- **Flips mesma local+seção, 2022 2ºT → 2026 1ºT (cross-turno): 12 flips
  estritos + 2 empates técnicos, todos no sentido direita** (zero para a
  esquerda). Estas são as seções-prioridade do 2º turno:
  - 1732 (Herondina): 411, 436, 446, 472, 475, 478, 482 (7 seções)
  - 1686 (Anexo/Capivari): 310, 438 (2 seções) + empate técnico 447
  - 1678 (Paschoal/Capivari): 287, 319, 423 (3 seções) + empate técnico 355
- **Novo (pipeline v2) — mesmo turno 2022 1ºT → 2026 1ºT (cobertura 97% por
  código): 16 flips, TODOS para a direita**, zero para a esquerda:
  1368/395; 1678: 264, 287, 319, 423; 1686: 310, 431, 438; 1732: 411, 425,
  436, 446, 472, 475, 478, 482.
- **Flips 2018 2ºT → 2022 2ºT: 5, todos para a esquerda** (1678×3: 287, 319,
  423; 1686/310; 1732/411) — o conjunto quase exato que devolveu à direita em
  2026. A geografia do swing 2018→2022 é a mesma do swing reverso 2022→2026.
- **Swing de share entre 2022 2ºT e 2026 1ºT (por local):** todos os 7 locais
  recuaram (−1,4 a −4,5 pp); os maiores recuos estão exatamente nas
  escolas-swing (1678: −4,5 pp; 1732: −4,4 pp).


## Matemática do 2º turno de 2026 (previsão, por conjunto)

- **Núcleo** (93 seções no T1, 34.882 aptos): comparecimento T1 74,8%;
  abstenções 8.783; **4.268 votos para virar** o T1 sem migração — fora de
  alcance por votos próprios. Cenários: base −18,7 pp; centro dividido 2:1
  para a direita (C/3, 2C/3) → L 10.120 × R 15.227 (−20,1 pp); base rate de
  2022 (n=81 seções nos 2 turnos) → −21,9 pp; base rate de 2018 (n=62,
  efeito Haddad) → L 23.526 × R 15.640 (+20,1 pp). Pool de comparecimento
  (abstenções + BN): 9.535.
- **Núcleo + fronteira 1368** (111 seções, 41.248 aptos): comparecimento
  75,0%; abstenções 10.306; **5.350 votos para virar**. Cenários: base
  −19,8 pp; centro 2:1 dir. → −21,1 pp; base rate 2022 (n=99) → −22,7 pp;
  base rate 2018 (n=80) → +17,2 pp. Pool: 11.261.

Cenários são hipóteses declaradas (migração assumida), não dados.

## Validação

- `T == QT_COMPARECIMENTO` nos arquivos do TSE: OK (469 seções conferidas).
- `aptos >= T`: OK. Nenhuma seção 2026 T1 com T < 60.

## Interpretação

- **Ingleses é mais conservador que Rio Vermelho e mais estável.** O bairro
  melhorou muito de 2018 (−64 pp) para 2022 (−9 pp no 1º turno), mas **nunca
  virou**: perdeu os dois turnos de 2022 e voltou a recuar em 2026 (−18,7 pp
  no 1º turno, share 40,7%). A base esquerda é sólida (≈40% do L×R) mas a
  direita nunca perdeu a maioria.
- **O 2º turno de 2022 foi negativo para a esquerda aqui** (−9,4 → −12,7 pp):
  diferente de Rio Vermelho (onde 2022 virou para a esquerda), o "efeito 2º
  turno" de 2022 em Ingleses consolidou a base bolsonarista. Não se pode
  presumir um swing automático de 2º turno em 2026 — ele tem que ser
  construído seção por seção.
- **Três escolas concentram a conversão possível:** 1678 (Paschoal/Capivari —
  a única que a esquerda **venceu** em 2022, +1,9 pp), 1686 (Anexo/Capivari,
  em crescimento: 5→8→15 seções entre 2018/2022/2026) e 1732 (Herondina, a
  maior, 25 seções/9.482 aptos, e o local com mais flips para a direita).
  Juntas: 49 seções, L = 5.228 × R = 6.695 (−13,2 pp) — para vencê-las todas
  seria preciso +1.468 votos; objetivo realista do 2º turno: **reverter
  1678 (como em 2022) e estancar 1686/1732**.
- **O resto do bairro (1562, 1600, 1376, 1643) está a 20–30 pp** para a
  direita: custo alto, não é prioridade de conversão — o papel dessas
  seções é **manter** a base (~35–40% share) e o comparecimento.
- **Crescimento do eleitorado:** aptos do núcleo subiram ~70% de 2018 para
  2026 (≈20,4 mil → 34,9 mil), concentrados em 1732 e 1686 — a periferia
  (Capivari/encosta) está votando mais; é onde a urbanização (Periferia Viva,
  contenção de encosta, esgoto) aparece de forma mais concreta no contraste
  entre os planos.
- **Comparecimento 2026:** ~71–86% por seção (média ≈ 75%) — há ~8–9 mil
  aptos que não votaram no 1º turno; parte é indecisão, parte é
  incomodidade/abdicação (em seção de direita, tende a ser a última).

- **Mesmo turno 2022 1ºT → 2026 1ºT: 16 flips, todos para a direita** (zero
  para a esquerda) — o recuo de 2026 não é artefato de "efeito 2º turno".

## Ressalvas

- 2026 é **somente 1º turno** (2º turno em 25/10/2026).
- Classificação de bairro por geocoding OSM/Nominatim (2 rodadas); as escolas
  sem resultado no OSM foram decididas pelo nome do bairro no nome da escola
  (1279 "PONTA DO MORRO") ou excluídas (1228, Sambaqui, baixa confiança).
- Números de seção são renumerados a cada eleição; os "flips" usam o mesmo
  critério da análise de Rio Vermelho (mesma local + mesmo nº) e podem
  incluir mudança de composição da seção.
- 1368 é fronteira Ingleses×Rio Vermelho (anexo 1686 = Ingleses/Capivari);
  evitar double counting ao somar com `../analise_riverio_v`.
- Candidatos: 2018 Haddad nº 13 × Bolsonaro nº 17; 2022 Lula 13 × Bolsonaro 22;
  2026 Lula 13 × Flávio Bolsonaro 22.

## Arquivos

- `detalhe_por_secao.csv` — 469 linhas, 18 colunas (ano, turno, local, nome,
  zona, seção, aptos, comparecimento, esquerda, direita, centro, esq3, dir3,
  branco_nulo, total, margem_esq_pp, esq_sobre_LpR_pct,
  polarizacao_LpR_sobre_T_pct) — todas as seções dos 8 locais nas três
  eleições.
- `config.json`, `config_aptos.json`, `conjuntos.json`, `nomes.json` —
  configurações exatas da execução de 2026-10-08 (reprodução com
  03_votos.py + 04_aptos.py + 05_analise.py da skill `flip-flavio-lula`,
  a partir do repositório).
