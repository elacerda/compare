# Ourofino (Ribeirão Pires/SP) — Evolução da polarização eleitoral 2018–2026

Análise dos votos na corrida presidencial (esquerda × direita) nas seções da
área **Ourofino** (Ribeirão Pires, ABC Paulista, SP), para as eleições de
**2018** (Haddad × Bolsonaro), **2022** (Lula × Bolsonaro) e
**2026 (1º turno)** (Lula × Flávio Bolsonaro).

Dados: arquivos oficiais do TSE (resultados por seção), em
`../eleicoes-{2018,2022,2026}/`. Detalhe em `detalhe_por_secao.csv`.

## Metodologia

1. **Zonas eleitorais.** Ribeirão Pires tem as zonas 183 (29 locais de
   votação) e 382 (8 locais); 262 seções em 2026. Os 5 locais analisados
   estão todos na zona 183 (a extração foi feita apenas com a zona 183).
2. **Identificação da área.** O TSE não tem campo de bairro. No OSM a área é
   rotulada como **"Ouro Fino Paulista"** (suburb, relation 3032213; polígono
   salvo em análise anterior) — é a única área com "Ouro Fino" no nome no
   município, no extremo leste (CEP 09407). Cada local de votação foi
   revisado manualmente: Nominatim/Photon (POI + endereço), ViaCEP (CEP) e
   distância até o polígono OSM da área.
3. **NÚCLEO (área alvo, 1 local, zona 183):**

   | local | local de votação | endereço | bairro/CEP | revisão |
   |---|---|---|---|---|
   | 1406 | EE Prof. Antônio Pádua Paschoal de Godoy | Estrada do Soma, 2950 | Ouro Fino Paulista (Vila Pereira Barreto) 09407-100 | POI dentro do polígono OSM "Ouro Fino Paulista"; o display_name do Nominatim cita "Ouro Fino Paulista" explicitamente |

4. **SENSIBILIDADE (EXT — 4 locais de fronteira da área):**

   | local | local de votação | endereço | revisão | tratamento |
   |---|---|---|---|---|
   | 1325 | EE Profª Marisa Afonso Salero | R. Graça, 90 | ~170 m do polígono OSM (N/NW da área) | fronteira — nunca entra no núcleo |
   | 1260 | EM IrMã Maria Bernadete Bandeira de Seixas | R. Recreio, 99 | ~300 m do polígono (Jd. Verão/Jd. Santa Luzia 09435-300) | fronteira |
   | 1112 | EE Profª Maria Pastana Menato | R. Prof. Antônio Nunes, 249 | ~400 m do polígono (Santa Rosa/Jd. Santa Luzia 09430-380) | fronteira |
   | 1066 | EE Profª Judith Ferreira Piva | Av. Miro Atílio Peduzzi, 140 | ~520 m do polígono (sem POI no OSM) | fronteira |

5. **Locais revisados e EXCLUÍDOS** (fora da área alvo): 1082 (EE Sen.
   Casemiro da Rocha, Rod. Índio Tibiriçá km 53,5 — Jardim Caçula 09161-405,
   fora do polígono), 1120 (EE Prof. João Gaudêncio Mainine, R. Pouso Alegre —
   sem resultado no OSM e sem evidência de pertencer à área), 1384 (EM
   Sebastião Vayego de Carvalho, Estrada do Taquaral — sem resultado no OSM),
   1473 (EE Dona Anna Lacevitta do Amaral, R. Orlando Schurachio, 277 — sem
   resultado no OSM), 1015 (EE Dom José Gaspar, R. Isidoro Fontes — "Centro
   Alto", fora da área), 1058 (EE Profª Leico Akaishi, R. Paula Cândido) e
   1147 (EE Alvaro de Souza Vieira, R. Princesa Isabel — sem resultado no
   OSM, POIs resolvidos fora do polígono).
6. **Convenções.** L = HADDA (2018) / LULA (2022, 2026); R = nome com
   BOLSONARO; O = demais candidatos + brancos + nulos. `margem` =
   (L−R)/(L+R)×100 (negativo = direita à frente). `share L` = L/(L+R)×100.
   `polarização` = (L+R)/T×100. 2026 tem apenas 1º turno (04/10/2026); o 2º
   turno foi em 25/10/2026.
7. **Estabilidade das seções.** Diferente de áreas com consolidação, aqui o
   número de seções por local é estável entre eleições (1406: 3 seções em
   2018 → 4 em 2022/2026; 1112: 16; 1066: 9 → 10; 1325: 8; 1260 existe desde
   2022, 1 seção). Flips são calculados na mesma `NR_LOCAL_VOTACAO` + número
   de seção (n=36 comuns em 2018×2022 e n=39 em 2022×2026).

## Resultados — núcleo (1406 EE Prof. Antônio Pádua Paschoal de Godoy — única escola dentro do bairro Ourofino)

| Eleição | Turno | Esquerda (L) | Direita (R) | Outros | Total | esq (L+R)/T | Margem (L−R)/(L+R) |
|---------|-------|-------------:|------------:|-------:|------:|------------:|-------------------:|
| 2018 | 1º | 131 | 366 | 349 | 846 | 58,7% | **−47,3 pp** |
| 2018 | 2º | 256 | 452 | 127 | 835 | 84,8% | **−27,7 pp** |
| 2022 | 1º | 414 | 465 | 151 | 1.030 | 85,3% | **−5,8 pp** |
| 2022 | 2º | 446 | 535 | 67 | 1.048 | 93,6% | **−9,1 pp** |
| 2026 | 1º | 329 | 516 | 166 | 1.011 | 83,6% | **−22,1 pp** |

Nota: 2018: Haddad × Bolsonaro; 2022: Lula × Bolsonaro; 2026: Lula × Flávio
Bolsonaro, apenas 1º turno (04/10/2026). Núcleo = 3 seções em 2018, 4 em
2022 e 4 em 2026 (seção 337 criada em 2022; aptos 2026: 1.290).

### Sensibilidade — EXT (núcleo + 4 locais de fronteira)

| Eleição | Turno | L | R | Outros | Total | esq (L+R)/T | Margem |
|---------|-------|---:|---:|-------:|------:|------------:|-------:|
| 2018 | 1º | 1.383 | 4.605 | 3.884 | 9.872 | 60,7% | −53,8 pp |
| 2018 | 2º | 2.796 | 5.667 | 1.349 | 9.812 | 86,3% | −33,9 pp |
| 2022 | 1º | 4.252 | 4.145 | 1.881 | 10.278 | 81,7% | +1,3 pp |
| 2022 | 2º | 4.639 | 4.997 | 717 | 10.353 | 93,1% | −3,7 pp |
| 2026 | 1º | 3.716 | 4.373 | 1.651 | 9.740 | 83,0% | −8,1 pp |

Locais somados no conjunto ampliado: 1325 (R. Graça), 1260 (R. Recreio),
1112 (R. Prof. Antônio Nunes) e 1066 (Av. Miro Atílio Peduzzi) — fronteiras
norte/noroeste/oeste da área. 33/35/35 seções em 2018/2022/2026 (aptos 2026:
12.344).

## Síntese dos números (ver `detalhe_por_secao.csv`)

- NÚCLEO (4 seções, 1.290 aptos em 2026): 2018 1T −47,3 pp → 2018 2T −27,7 pp
  → 2022 1T −5,8 pp → 2022 2T −9,1 pp → **2026 1T −22,1 pp** (L 329 × R 516).
  Share de L: 26,4% → 36,2% → 47,1% → 45,5% → **38,9%** (−6,5 pp em 2026 —
  o núcleo, que quase empatou em 2022, voltou para a direita).
- EXT: 2018 1T −53,8 → 2018 2T −33,9 → 2022 1T **+1,3** → 2022 2T −3,7 →
  2026 1T −8,1 pp (L 3.716 × R 4.373). Em 2022 o 1º turno foi o único turno
  com a esquerda à frente — e no 2º turno a direita recuperou (padrão de
  crossover à direita).
- **Contração das seções de esquerda:** 21 seções à esquerda em EXT no 1º
  turno de 2022 → 9 no 2º turno de 2022 → **5 no 1º turno de 2026**
  (1066/44 +1,0 pp; 1325/292 +3,1 pp; 1112/126 +4,5 pp; 1066/45 +5,5 pp;
  1066/46 +5,8 pp).
- Por local (2026 1T): 1066 **−4,8** (mais competitivo) · 1325 −7,8 ·
  1112 −9,7 · 1260 −16,6 (1 seção) · 1406 −22,1.
- **22 seções com |margem| ≤ 10 pp em 2026** (agregado L 2.433 × R 2.628,
  −3,9 pp): 1066 (329, 44, 45, 46, 47, 118, 140, 335), 1112 (126, 131, 182,
  191, 194, 200, 246, 256, 262), 1325 (230, 241, 278, 292, 297).
- **Flips 2018 2T → 2022 2T** (n=36): 9 para a esquerda
  (1066: 44, 46, 140; 1112: 126, 131, 194, 246, 262; 1325: 292), 0 para a
  direita. **Flips 2022 2T → 2026 1T** (n=39): 5 para a direita
  (1066/140; 1112/131, 194, 246, 262 — a maioria das que tinham virado para a
  esquerda em 2022) e 1 para a esquerda (1066/45).
- Swing de share de L por local (último turno de cada ano): 1066 33,8% →
  48,9% → 47,6% (Δ −1,3 pp 2022→2026) · 1112 31,6% → 48,5% → 45,2% (Δ −3,3) ·
  1325 35,1% → 46,9% → 46,1% (Δ −0,8) · 1406 36,2% → 45,5% → 38,9% (Δ −6,5).
- **Matemática do 2º turno (2026):** NÚCLEO L 329 × R 516 → votos para virar
  (R−L) = **187**; EXT L 3.716 × R 4.373 → **657**. Sanity check: o swing
  1T→2T de 2018 nas 36 seções comuns foi L +1.538 × R +1.148 (líquido +390
  para L) — a magnitude de crossover de 2º turno que **já aconteceu** neste
  território, mesmo com derrota em 2018.
- Comparecimento 2026 1T: núcleo 1.011/1.290 aptos (78,4%); EXT
  9.740/12.344 (78,9%) — ~2.883 aptos não votaram nos 5 locais, além de 1.817
  brancos/nulos.
- Estratégia completa: `estrategia-flip-ourofino-ribeiraopires.md` (nesta pasta).
