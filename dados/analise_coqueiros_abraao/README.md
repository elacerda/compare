# Coqueiros + Abraão (Florianópolis/SC, continente) — Evolução da polarização eleitoral 2018–2026

Análise dos votos na corrida presidencial (esquerda × direita) nas seções dos
**distritos de Coqueiros e Abraão** (parte continental de Florianópolis, SC),
para as eleições de **2018** (Haddad × Bolsonaro), **2022** (Lula × Bolsonaro)
e **2026 (1º turno)** (Lula × Flávio Bolsonaro).

Dados: arquivos oficiais do TSE (resultados por seção), em
`../eleicoes-{2018,2022,2026}/`. Detalhe em `detalhe_por_secao.csv`.

## Metodologia

1. **Zonas eleitorais.** Florianópolis tem zonas 12, 13 e 100. A parte
   continental está nas zonas 12 e 13 (a 100 cobre a porção oeste/norte da Ilha).
   As 98 escolas das duas zonas foram listadas (`01_locais.py`) e geocodificadas
   (OSM/Nominatim, `02_geocode.py`) para inferir o bairro.
2. **Identificação do bairro.** O TSE não tem campo de bairro; os locais de
   votação são escolas/igrejas/órgãos identificados por endereço. Cada local foi
   revisado manualmente (display_name completo + CEP). Faixas usadas:
   Coqueiros = 88080-xxx; Abraão = 88085-xxx (OSM rotula "Abraão, Coqueiros");
   Pântano do Sul = 88067-xxx; Coloninha/Capoeiras/Jardim Atlântico (Estreito) = 88090/88070.
3. **NÚCLEO (bairros alvo, 5 locais, zona 12):**

   | local | local de votação | endereço | bairro/CEP | revisão |
   |---|---|---|---|---|
   | 2097 | EEB Rosinha Campos | R. Joaquim Fernandes de Oliveira, 428 | Abraão (Coqueiros) 88085-170 | rua+nº; confirmada por query direta da rua |
   | 2100 | EBM Almirante Carvalhal | R. Bento Góia, 113 | Saco da Lama (Coqueiros) 88080-150 | rua+nº |
   | 2143 | EEB Presidente Roosevelt | R. Pascoal Simone, 80 | Coqueiros 88080-350 | POI + rua confirmada |
   | 2216 | Paróquia Igreja N. Sra. do Carmo | R. Prof. Bayer Filho, 81 | N. Sra. Aparecida (Coqueiros) 88080-250 | rua+nº |
   | 2054 | CEFID/UDESC (C. Ciências da Saúde e do Esporte) | R. Paschoal Simone, 358 | Coqueiros (inferência) | sem POI no OSM; mesma rua da 2143 (segmentos 88080-250/350) — inferência documentada |

4. **REGIÃO (sensibilidade, NÚCLEO + 6 locais de fronteira/adjacência):**

   | local | local de votação | bairro/CEP | zona | tratamento |
   |---|---|---|---|---|
   | 2038 | IFSC Continente | R. 14 de Julho, 150 — OSM: Estreito, mas CEP 88080-010 (faixa Coqueiros) | 12 | **fronteira com conflito** → nunca entra no núcleo |
   | 2429 | IFSC Continente II | idem (mesmo campus) | 12 | idem |
   | 2160 | EEB Edith Gama Ramos | Capoeiras Oeste (Capoeiras/Estreito) | 12 | fronteira oeste de Coqueiros (POI) |
   | 2461 | FUCAS | Capoeiras Leste 88085-000 | 12 | fronteira oeste de Coqueiros |
   | 1384 | EEB Severo Honorato da Costa | Pântano do Sul 88067-102 | 13 | adjacente a Abraão (sul) |
   | 1406 | EBM Costa de Dentro | Pântano do Sul 88067-130 | 13 | adjacente a Abraão (sul) |

5. **Locais revisados e EXCLUÍDOS** (fora dos bairros alvo): 1287 (José Mendes,
   88020-200 — continente central), 1392 (Rod. Francisco Thomas dos Santos,
   direção Armação/Sambaetê), 1295/1309/1589/1899 (Saco dos Limões/Costeira do
   Pirajubaé), 1317/1325/1333/2038-z13 (Carianos/Tapera da Base), 2348 (sem
   resultado no OSM), e as escolas de Coloninha/Jardim Atlântico/Canto/Capoeiras
   interior (2070, 2127, 2135, 2151, 2178, 2186, 2208, 2224, 2356, 2364, 2445,
   2470, 2500) — Estreito, sem vínculo com o alvo.
6. **Colisão de `NR_LOCAL_VOTACAO` entre zonas (cuidado!):** 2038 existe nas
   zonas 12 (IFSC Continente) e 13 (NEIM Idalina Ochôa, Carianos); também colidem
   1686, 1716, 1732, 1740, 1767, 1775, 1783, 1805, 1813, 2046. Por isso a extração
   foi feita em 3 configs separados por zona (`config_nucleo.json` zona 12 núcleo,
   `config_ext12.json` zona 12 fronteira, `config_ext13.json` zona 13 Pântano do
   Sul) e os TSVs foram concatenados — nenhum local selecionado colide entre os
   conjuntos.
7. **Convenções.** L = HADDA (2018) / LULA (2022, 2026); R = nome com BOLSONARO;
   O = demais candidatos + brancos + nulos. `margem` = (L−R)/(L+R)×100 (negativo
   = direita à frente). `share L` = L/(L+R)×100. `polarização` = (L+R)/T×100.
   2026 tem apenas 1º turno (04/10/2026).
8. **Limitação de vinculação.** Seções são renumeradas a cada eleição; flips só
   são calculados para a mesma `NR_LOCAL_VOTACAO` + número de seção.

## Resultados — núcleo (5 locais: Rosinha Campos/Abraão, Almirante Carvalhal/Saco da Lama, Pres. Roosevelt, Igreja N. Sra. do Carmo, CEFID/UDESC)

| Eleição | Turno | Esquerda (L) | Direita (R) | Outros | Total | esq (L+R)/T | Margem (L−R)/(L+R) |
|---------|-------|-------------:|------------:|-------:|------:|------------:|-------------------:|
| 2018 | 1º | 1.748 | 8.138 | 5.722 | 15.608 | 63,3% | **−64,6 pp** |
| 2018 | 2º | 4.633 | 9.531 | 1.270 | 15.434 | 91,8% | **−34,6 pp** |
| 2022 | 1º | 6.201 | 7.847 | 2.518 | 16.566 | 84,8% | **−11,7 pp** |
| 2022 | 2º | 6.870 | 9.057 | 626 | 16.553 | 96,2% | **−13,7 pp** |
| 2026 | 1º | 5.752 | 7.713 | 2.049 | 15.514 | 86,8% | **−14,6 pp** |

Nota: 2018: Haddad × Bolsonaro; 2022: Lula × Bolsonaro; 2026: Lula × Flávio
Bolsonaro, apenas 1º turno (04/10/2026). A composição do núcleo muda
ligeiramente entre eleições (seções renumeradas): 50 seções em 2018, 51 em
2022 e 52 em 2026 (novas seções na Rosinha Campos/Abraão).

### Sensibilidade — região (núcleo + 6 locais de fronteira/adjacência)

| Eleição | Turno | L | R | Outros | Total | esq (L+R)/T | Margem |
|---------|-------|---:|---:|-------:|------:|------------:|-------:|
| 2018 | 1º | 2.514 | 11.307 | 7.988 | 21.809 | 63,4% | −63,6 pp |
| 2018 | 2º | 6.513 | 13.302 | 1.811 | 21.626 | 91,6% | −34,3 pp |
| 2022 | 1º | 9.177 | 11.270 | 3.526 | 23.973 | 85,3% | −10,2 pp |
| 2022 | 2º | 10.120 | 12.926 | 885 | 23.931 | 96,3% | −12,2 pp |
| 2026 | 1º | 9.649 | 12.459 | 3.388 | 25.496 | 86,7% | −12,7 pp |

Locais somados no conjunto ampliado: IFSC Continente (2038), IFSC Continente
II (2429), EEB Edith Gama Ramos (2160), FUCAS (2461) — fronteiras oeste;
EEB Severo Honorato da Costa (1384) e EBM Costa de Dentro (1406) —
Pântano do Sul, adjacente a Abraão. 72/76/88 seções em 2018/2022/2026.

## Síntese dos números (ver `detalhe_por_secao.csv`)

- NÚCLEO (52 seções, 18.835 aptos em 2026): 2018 1T −64,6 pp → 2018 2T −34,6 pp →
  2022 1T −11,7 pp → 2022 2T −13,7 pp → 2026 1T −14,6 pp (L 5.752 × R 7.713).
- Região é **conservadora e nunca virou para a esquerda** (diferente de Rio
  Vermelho): em 2022 o 2º turno foi *pior* que o 1º (−11,7 → −13,7 pp).
- 2018→2022: swing de +6 a +15,5 pp de share de L em todos os locais; 2022→2026:
  estável a levemente negativo (exceto IFSC +7,2 pp).
- Bolsões de competitividade em 2026 1T: IFSC Continente (2038 +0,8 pp; 2429
  +11,9 pp), Pântano do Sul (1406 +4,3 pp; 1384 −1,4 pp) e a escola de Abraão
  (2097 −8,0 pp, com 8 das 16 seções próximas do NÚCLEO).
- Estratégia completa: `../estrategia-flip-coqueiros-abraao.md`.

### Seções 2026 (núcleo) e "flips"

- 2026 1º turno, núcleo (52 seções): **1 seção à esquerda × 51 à direita**
  (Rosinha Campos/Abraão: 1 L / 11 R; Almirante Carvalhal/Saco da Lama:
  0 L / 11 R; Pres. Roosevelt: 0 L / 12 R; Igreja N. Sra. do Carmo:
  0 L / 7 R; CEFID/UDESC: 0 L / 10 R). A única seção de esquerda do núcleo
  é a 2097/seção 647 (129 × 126, +1,2 pp — empate técnico). Na região
  completa: 10 L × 78 R. Detalhes em `detalhe_por_secao.csv`.
- Mesmo local + mesmo número de seção (nenhum flip no núcleo; todos em
  locais da região):
  - 2018 2ºT → 2022 2ºT: 3 flips, todos para a esquerda, todos em Pântano
    do Sul (1384/221, 1384/267 e 1406/339).
  - 2022 2ºT → 2026 1ºT: 6 flips — 4 para a esquerda (2038/655, 2429/657,
    1384/222 e 1384/321) e 2 para a direita (1384/221 e 1384/267, as
    mesmas que tinham virado para a esquerda em 2022).
