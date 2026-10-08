# Centro Histórico + Fazenda do Max + Praia Comprida (São José/SC) — Evolução da polarização eleitoral 2018–2026

Análise dos votos na corrida presidencial (esquerda × direita) nas seções da
área **Centro Histórico + Fazenda do Max + Praia Comprida**, São José (SC),
para as eleições de **2018** (Haddad × Bolsonaro), **2022** (Lula × Bolsonaro)
e **2026 — somente 1º turno** (Lula × Flávio Bolsonaro).

Dados: arquivos oficiais do TSE (resultados por seção), em
`../eleicoes-{2018,2022,2026}/`. Detalhe por seção em `detalhe_por_secao.csv`.
A estratégia de 2º turno derivada desta análise:
`estrategia-saojose-centro-fazendamax-praiacomprida.md` (nesta pasta).

## Metodologia

1. **Zona eleitoral.** Os 3 bairros alvo de São José (cód. 42075) têm os
   locais de votação na **zona 29**. Os 49 locais da zona foram geocodificados
   e revisados individualmente; os 11 da análise (5 NÚCLEO + 6 EXT) são os
   únicos dentro dos 3 bairros alvo ou na sua fronteira imediata.
2. **Identificação da área.** O TSE não traz o nome do bairro; os locais são
   escolas identificadas por endereço. Cada local da zona 29 foi geocodificado
   no OSM/Nominatim (1 req/s, User-Agent identificável; 2 rodadas em
   06–07/10/2026) e classificado por **point-in-polygon** contra 4 relações
   OSM: "Centro Histórico" (relation **6954970** — o bairro-alvo; centroid na
   R. Padre Macário, 88103-043; borda leste no Calçadão Beira Mar; borda oeste
   na BR-282/Rod. Mário Covas), "Praia Comprida", "Fazenda Santo Antônio" e
   "Centro Histórico de São José". **Atenção ao rótulo OSM:** a relação
   "Centro Histórico de São José" cobre **todo o distrito** de São José (nome
   enganoso) — foi usada apenas como cross-check, nunca para incluir locais.
   A revisão manual local por local está registrada em
   `geocode.tsv.folha.tsv` (status + CEP + evidência).
3. **"Fazenda do Max".** Não existe "Fazenda do Max" no OSM. A página da
   Wikipedia de São José/SC registra que parte das terras de **Max Habitzel**
   deu origem à **Fazenda Santo Antônio** (bairros Santo Antônio/Água Doce,
   entorno do antigo parque industrial). **Inferência declarada:**
   "Fazenda do Max" ≈ polígono OSM "Fazenda Santo Antônio" — os 2 locais
   (1104, 1627) caem dentro dele e têm CEP 88104 (faixa do bairro).
4. **NÚCLEO (5 locais, todos dentro dos polígonos OSM dos 3 bairros):**

   | local | local de votação | endereço TSE | bairro/CEP (revisão) | 2026 |
   |---|---|---|---|---|
   | 1597 | IFSC Campus São José | R. José Lino Kretzer, 608 | Centro Histórico, 88130-310 — POI dentro da relation 6954970 | 14 seções, 4.415 aptos |
   | 1104 | EBM Veread. Albertina Krummel Maciel | R. Adélio Longo, 675 | Fazenda Santo Antônio ("Fazenda do Max"), 88104-400 — dentro do polígono | 10 seções, 3.734 aptos |
   | 1627 | CEI Santo Antônio | R. Nereu Neto Capistrano, S/N | Fazenda Santo Antônio, 88104-574 — dentro do polígono | 6 seções, 2.236 aptos |
   | 1660 | EEB Profª Maria José Barbosa Vieira | R. Joaquim Vaz, 1413 | Praia Comprida, 88102-650 — dentro do polígono | 5 seções, 1.862 aptos |
   | 1708 | Faculdade Anhanguera | R. Luiz Fagundes | Praia Comprida, 88103-445 — dentro do polígono (POI) | 2 seções, 715 aptos |

   Total 2026: **37 seções, 12.962 aptos** (comparecimento 80,1%).
5. **EXT / sensibilidade (6 locais verificados, adjacentes — fronteira,
   distância máxima ~1,6 km do polígono alvo):**

   | local | local de votação | bairro/CEP (revisão) | distância | 2026 |
   |---|---|---|---|---|
   | 1066 | EEB Nossa Sra. da Conceição | Roçado, 88108 | ~304 m de Praia Comprida | 14 seções, 5.342 aptos |
   | 1260 | EEB Profª Laurita Dutra de Souza | Picadas do Sul, 88106-260 | ~1,0 km | 13 seções, 4.808 aptos |
   | 1422 | EEF Profª Marcília de Oliveira | Forquilhinha, 88106-600 | ~1,0–1,6 km | 14 seções, 5.360 aptos |
   | 1619 | CEM Antônio Francisco Machado | Forquilhinha, 88106-517 | ~1,0–1,6 km | 14 seções, 5.530 aptos |
   | 1511 | Igreja de Santo Antônio | Campinas, 88101-290 | ~1,5 km | 7 seções, 2.463 aptos |
   | 1740 | Colégio Gardner | Campinas/Kobrasol, 88102-250 | ~1,1 km | 7 seções, 2.571 aptos |

   Total 2026: **69 seções, 26.074 aptos** (comparecimento 80,5%).
   **1708 e 1740 existem apenas em 2026** (sem seções em 2018/2022).
6. **Excluídos (verificados como fora dos 3 bairros):** 31 locais do distrito
   de **Barreiros** (Ipiranga, Bela Vista, Areias, Serraria, N. Sra. do
   Rosário, Real Parque, Jardim Santiago — 3 a 10 km ao sul; ex.: 1015, 1031,
   1058, 1163, 1198, 1287, 1309), **Alto Forquilhas** (1392), **Potecas**
   (1600, 1635), **Forquilhas Leste** (1589, 1651, 1732), **Colônia Santana**
   (1570, 1686 — ~8,7 km ao norte) e **1317** (Estácio de Sá: o endereço TSE
   "R. Leoberto Leal, 431" gerou hit de rua em outra cidade — São Joaquim/SC;
   o POI da faculdade está na R. Laudelino Souza Filho, 431, **Barreiros**,
   88117-473) e **1325** (C.M. Luar: POI em **Serraria**, Barreiros, ~7 km).
7. **Não verificados (sem resultado no OSM) — excluídos:** 1210 (R. Alan
   Kardec, Forquilhinha, fora da área — confiança baixa), 1341 (Jd. Solimar),
   1384 (Maria Luiza de Melo), 1643 (Av. Lisboa — mesma rua dos 1589/1651,
   Forquilhas Leste), 1716 (Escola Profissional de Campinas — bairro vizinho,
   já coberto por 1511/1740 no EXT), 1724 (CEI Ondina Schmidt Gerlach), 1759
   (Igreja São Francisco e Santa Rita). **Nenhum deles tem seção em
   2018/2022/2026** (conferido no CSV do TSE) — zero impacto nos números.
8. **Convenções.** L = Haddad (2018) / Lula (2022, 2026); R = Bolsonaro
   (2018, 2022) / Flávio Bolsonaro (2026); margem = (L−R)/(L+R) em pp
   (negativo = direita à frente); share L = L/(L+R); polarização = (L+R)/T.
   "Outros" é decomposto em C (centro/coluna C), E (3º de esquerda),
   N (3º de direita), BN (branco + nulo) — coluna por coluna no CSV.
9. **Estabilidade e matching entre eleições.** Todos os locais do NÚCLEO
   (exceto 1708, 2026-only) mantêm **mesma escola + mesmo endereço** em
   2018/2022/2026. Seções são casadas por `NR_LOCAL_VOTACAO` + nº de seção
   (o TSE **renumera seções a cada eleição** — limitação de fato declarada).
   Cobertura de matching: 2018 T1 × 2022 T1: 90/90 (100%); 2022 T1 × 2026 T1
   e 2022 T2 × 2026 T1: 94 por código (97%; 3 seções de 2022 sem par). Zero
   pares casados só por nome — todo flip é **estrito** (código).
10. **Limitação de vinculação.** A seção acompanha a **escola** (local de
    votação), não o domicílio do eleitor — um morador de outro bairro pode
    votar aqui. Aceita e declarada.

## Resultados — NÚCLEO (5 locais, 37 seções, 12.962 aptos em 2026)

| Eleição | Turno | Esquerda (L) | Direita (R) | Outros | Total | esq (L+R)/T | Margem (L−R)/(L+R) | Share L |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 2018 | 1º | 862 | 5.049 | 3.102 | 9.013 | 65,6% | **−70,8 pp** | 14,6% |
| 2018 | 2º | 2.241 | 5.910 | 755 | 8.906 | 91,5% | **−45,0 pp** | 27,5% |
| 2022 | 1º | 3.309 | 4.956 | 1.437 | 9.702 | 85,2% | **−19,9 pp** | 40,0% |
| 2022 | 2º | 3.566 | 5.720 | 425 | 9.711 | 95,6% | **−23,2 pp** | 38,4% |
| 2026 | 1º | 3.206 | 5.688 | 1.495 | 10.389 | 85,6% | **−27,9 pp** | 36,0% |

## Resultados — EXT / sensibilidade (6 locais, 69 seções, 26.074 aptos em 2026)

| Eleição | Turno | Esquerda (L) | Direita (R) | Outros | Total | esq (L+R)/T | Margem (L−R)/(L+R) | Share L |
|---|---|---:|---:|---:|---:|---:|---:|---:|
| 2018 | 1º | 1.991 | 11.139 | 6.118 | 19.248 | 68,2% | −69,7 pp | 15,2% |
| 2018 | 2º | 4.637 | 12.810 | 1.630 | 19.077 | 91,5% | −46,8 pp | 26,6% |
| 2022 | 1º | 6.445 | 10.830 | 2.848 | 20.123 | 85,8% | −25,4 pp | 37,3% |
| 2022 | 2º | 6.987 | 12.445 | 746 | 20.178 | 96,3% | −28,1 pp | 36,0% |
| 2026 | 1º | 6.198 | 12.024 | 2.764 | 20.986 | 86,8% | −32,0 pp | 34,0% |

### Decomposição de "Outros" — 2026 1º turno

| Conjunto | Centro (C) | 3º esq (E) | 3º dir (N) | Branco+Nulo (BN) |
|---|---:|---:|---:|---:|
| NÚCLEO | 1.123 | 0 | 0 | 372 |
| EXT | 2.065 | 0 | 0 | 699 |

## Por local (último turno de cada ano)

| Local | Bairro | 2018 2ºT (margem, share L) | 2022 2ºT (margem, share L) | 2026 1ºT (L × R, margem, share L) | aptos 2026 |
|---|---|---|---|---|---:|
| 1597 | Centro Histórico | −41,9 pp, 29,0% | −24,1 pp, 38,0% | 1.101 × 2.025 (−29,6 pp, 35,2%) | 4.415 |
| 1104 | Fazenda do Max | −51,4 pp, 24,3% | −30,6 pp, 34,7% | 831 × 1.733 (−35,2 pp, 32,4%) | 3.734 |
| 1627 | Fazenda do Max | −45,5 pp, 27,3% | −20,6 pp, 39,7% | 529 × 985 (−30,1 pp, 34,9%) | 2.236 |
| 1660 | Praia Comprida | −34,7 pp, 32,7% | **−4,5 pp, 47,8%** | 525 × 658 (−11,2 pp, 44,4%) | 1.862 |
| 1708 | Praia Comprida | — | — | 220 × 287 (−13,2 pp, 43,4%) | 715 |
| 1066 (EXT) | Roçado | −47,2 pp, 26,4% | −31,5 pp, 34,2% | 1.167 × 2.510 (−36,5 pp, 31,7%) | 5.342 |
| 1260 (EXT) | Picadas do Sul | −46,6 pp, 26,7% | −28,0 pp, 36,0% | 1.137 × 2.264 (−33,1 pp, 33,4%) | 4.808 |
| 1422 (EXT) | Forquilhinha | −48,4 pp, 25,8% | −30,9 pp, 34,5% | 1.226 × 2.709 (−37,7 pp, 31,2%) | 5.360 |
| 1619 (EXT) | Forquilhinha | −40,2 pp, 29,9% | −16,8 pp, 41,6% | 1.333 × 2.246 (−25,5 pp, 37,2%) | 5.530 |
| 1511 (EXT) | Campinas | −50,0 pp, 25,0% | −32,7 pp, 33,6% | 599 × 1.191 (−33,1 pp, 33,5%) | 2.463 |
| 1740 (EXT) | Campinas/Kobrasol | — | — | 736 × 1.104 (−20,0 pp, 40,0%) | 2.571 |

## Seções 2026 1º turno — próximas e "flips"

- **Seções próximas (|margem| ≤ 10 pp, T ≥ 60): 7 no total**, agregado
  **L 824 × R 892 (−4,0 pp)**, T = 2.013: 1740/390 (−3,5), 1708/410 (−3,6),
  1619/392 (**+3,8 — única à esquerda**), 1660/381 (−4,0), 1740/386 (−4,1),
  1660/398 (−6,5), 1627/384 (−9,8). Cada uma com ±6,1 a ±6,7 pp (1σ).
  Se a zona virasse 50×50: +68 no diferencial; 55×45 (teto): **+269**.
- **Flips 2022 1ºT → 2026 1ºT (mesmo código, cobertura 97%): 4, TODOS
  esquerda→direita** (zero no sentido inverso): 1660/371, 1660/381,
  1627/384, 1619/385. **Cross-turno 2022 2ºT → 2026 1ºT: 3** (1660/381,
  1627/384, 1619/385) — 1660/381 **vencia a esquerda por +38 votos no 2º
  turno de 2022** e está a −9 em 2026: a seção mais virada da área.
- **Flips 2018 1ºT → 2022 1ºT: 1, direita→esquerda** (1660/371 — a geografia
  do swing 2018→2022 é a mesma da reversão 2022→2026). 2018 2ºT → 2022 2ºT:
  1 (1619/379, E→D).
- **Escola-swing: 1660 (Praia Comprida)** — a única do NÚCLEO que se
  aproximou do empate: −34,7 pp (2018 2ºT) → **−4,5 pp (2022 2ºT, share L
  47,8%)** → −11,2 pp (2026 1ºT, 44,4%). Swing de share L por local
  2018→2022: +7,8 a **+15,1 pp (1660)**; 2022→2026: −0,2 a **−4,8 pp
  (1627)** — recuo geral, maior nas escolas com flips.

## Matemática do 2º turno (2026) — calculada pelo 05

**NÚCLEO (37 seções, 12.962 aptos):**
- 1ºT: L 3.206 × R 5.688 (−27,9 pp); C 1.123, BN 372; comparecimento 80,1%;
  abstenções 2.573.
- **Votos p/ virar (1ºT, sem migração): 2.482** — exigir ~24 pp de swing:
  **fora de alcance**; a meta é decomposta (ver estratégia §1/§6).
- Cenários 2T (**hipóteses declaradas**, exceto base rates):
  - base (sem migração): L 3.206 × R 5.688 (−27,9 pp)
  - centro 2:1 p/ direita (C/3 p/ L, 2C/3 p/ R): L 3.580 × R 6.437 (−28,5 pp)
  - **base rate 2022** (n=33 seções nos 2 turnos, medido): L×1,08, R×1,15 →
    L 3.455 × R 6.565 (**−31,0 pp** — o 2º turno de 2022 aqui foi *negativo*
    para a esquerda: −19,9 → −23,2 pp)
  - **base rate 2018** (n=30, medido): L×2,60, R×1,17 → L 8.335 × R 6.658
    (**+11,2 pp** — magnitude de swing que já aconteceu nesta área em 2018)
- **Pool de comparecimento:** abstenções 2.573 + BN 372 = **2.945** aptos
  candidatos a comparecimento no 2º turno.

**EXT (69 seções, 26.074 aptos):** 1ºT L 6.198 × R 12.024 (−32,0 pp); votos
p/ virar **5.826** (fora de alcance); cenários: base −32,0 pp; centro 2:1
−32,1 pp; base rate 2022 (n=64) −34,6 pp; base rate 2018 (n=60) +2,1 pp;
pool de comparecimento 5.787 (abstenções 5.088 + BN 699).

## Interpretação

- **A área é swing de verdade, mas oscila para baixo.** De −70,8 pp (2018
  1ºT) para −19,9 pp (2022 1ºT) — o maior salto da amostra — e recuou para
  −27,9 pp em 2026. A base esquerda é real (share 36–40% no 1º turno desde
  2022) mas a direita nunca perdeu a maioria no NÚCLEO.
- **O 2º turno não é automático aqui.** Em 2022 o 2º turno *aprofundou* a
  margem da direita (−19,9 → −23,2 pp; base rate L×1,08/R×1,15). Em 2018 o
  2º turno virou o sinal para a esquerda no conjunto (L×2,60) — o swing de
  2º turno de 2018 (+2.379 votos em L no NÚCLEO) mostra que a magnitude
  necessária **já aconteceu nesta área**, no contexto Bolsonaro×Haddad.
- **A conversão se concentra em 3 escolas:** 1660 (a escola-swing de Praia
  Comprida), 1627 (CEI de Fazenda do Max — share 39,7% em 2022, flip em
  2026) e 1619 (EXT de Forquilhinha — a melhor margem da fronteira, −16,8 pp
  em 2022). O resto do NÚCLEO (1104, 1597) está a 25–35 pp: papel de
  **manutenção de base + comparecimento**.
- **Comparecimento ~75–84% por local em 2026** — 2.573 aptos do NÚCLEO não
  votaram; parte é indecisão (mobilizar rende sem "vencer" ninguém).

## Ressalvas

- 2026 é **somente 1º turno** (2º turno em 25/10/2026) — os cenários de 2º
  turno são **previsão** (hipóteses declaradas), exceto os base rates 2018/
  2022, que são medidos.
- Seções são renumeradas a cada eleição; os flips usam o mesmo critério de
  Rio Vermelho/Ingleses (mesmo local + mesmo nº de seção) e podem incluir
  mudança de composição da seção. Cobertura de matching declarada (§9).
- "Fazenda do Max" ≈ "Fazenda Santo Antônio" é **inferência** (Wikipedia);
  os 2 locais do bairro caem dentro do polígono OSM e têm CEP da faixa.
- 7 locais sem resultado no OSM foram excluídos; nenhum tem seção em
  2018/2022/2026 (zero impacto nos números).
- 1708 e 1740 são locais novos (somente 2026) — sem histórico comparável.
- Bairro por geocodificação OSM/Nominatim + point-in-polygon, com revisão
  manual registrada em `geocode.tsv.folha.tsv`.

## Planos de governo (proveniência)

- Flávio (PL) — "Para o Brasil Vencer o Atraso", **76 págs.** — PDF:
  `../../FLAVIO-BOLSONARO-PARA-O-BRASIL-VENCER-O-ATRASO.pdf`
  (sha256 `ff60b7ae45083471448af7fa0bf62bbe7ce209a1d21682b3482f142e0cb8b4f0`)
- Lula (PT) — "Diretrizes para o Programa de Transformação do Brasil",
  **84 págs.** — PDF: `../../Programa-Governo-LULA-2026.pdf`
  (sha256 `75e2dab7b9af27454a5c1a44c3bb0d7e0eaddbd1c355ccf1536f0d0be927e47b`)
- Origem: PDFs no raiz do workspace (sem URL oficial registrada); páginas
  conforme numeração do PDF.
- Extração com `06_planos.py` (rodada de 08/10/2026, com cabeçalho de
  proveniência no txt): 76 págs./2.026.010 bytes (Flávio) e 84
  págs./3.085.792 bytes (Lula). Contagens de lacuna confirmadas pela saída
  oficial do 06: Flávio — farmácia 0 (radical —), genéric 0 (—), insulina
  0 (—), medicamento 0 (—), "salário mínimo" 0 (—); remédio 4 + remédios 1.
  Lula — farmácia 3, medicamento 5, insulina 1, "salário mínimo" 1.

## Arquivos

- `detalhe_por_secao.csv` — 480 linhas (ano, turno, local, seção, aptos,
  comparecimento, L, R, C, E, N, BN, total, margem, share L, polarização)
- `analise_stdout.txt` — relatório completo do 05_analise.py
- `config.json`, `config_aptos.json`, `conjuntos.json`, `nomes.json` —
  reprodutibilidade (03/04/05)
- `geocode.tsv` + `geocode.tsv.folha.tsv` — geocodificação + **folha de
  revisão preenchida** (49 locais, status + obs)
- `estrategia-saojose-centro-fazendamax-praiacomprida.md` — estratégia
  de 2º turno derivada desta análise

## Validação (05)

- T == QT_COMPARECIMENTO: **OK (480 seções conferidas)**
- aptos ≥ T: **OK**
- seções com T < 60 no 2026 1ºT: 0 (fora das "próximas" por ruído)
