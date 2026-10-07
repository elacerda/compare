# Rio Vermelho (Florianópolis/SC) — Evolução da polarização eleitoral 2018–2026

Análise dos votos na corrida presidencial (esquerda × direita) nas seções da
**zona 100** localizadas no bairro **Rio Vermelho**, Florianópolis (SC), para as
eleições de **2018** (Haddad × Bolsonaro), **2022** (Lula × Bolsonaro) e
**2026** (Lula × Flávio Bolsonaro).

Dados: arquivos oficiais do TSE (resultados por seção), baixados em
`dados/eleicoes-2018/`, `dados/eleicoes-2022/` e `dados/eleicoes-2026/`.

## Metodologia

1. **Zona eleitoral.** Florianópolis (cód. município 81051) tem zonas 12, 13 e
   100. A zona 100 abrange 397 seções da porção oeste/norte da Ilha (Jurerê,
   Ingleses, Canasvieiras, Lagoa, Saco Grande, Ponta do Morro, Rio Vermelho…).
2. **Identificação do bairro.** A string "VERMELHO" não aparece em nenhum campo
   dos arquivos do TSE; os locais de votação são escolas, identificadas por
   endereço. Cada escola da zona 100 foi geocodificada (OSM/Nominatim) e o
   bairro foi inferido pelo CEP do endereço (Rio Vermelho = CEP 88060-xxx;
   o sub-bairro Muquém faz parte do Rio Vermelho).
3. **Conjunto de seções (núcleo / "core"):**
   - `NR_LOCAL_VOTACAO 1503` — EEB de Muquém (Rua Manoel Petronilho da Silveira
     1, CEP 88060-132). Presente em 2018, 2022 e 2026.
   - `NR_LOCAL_VOTACAO 1929` — EBM Darcy Ribeiro (POI CEP 88060-338). **Somente
     2026** (local novo).
   - 2026: 20 seções no núcleo (13 na EEB de Muquém + 7 na EBM Darcy Ribeiro).
4. **Conjunto ampliado (sensibilidade / "ext"):** núcleo + `1368` (EEB
   Intendente José Fernandes), seu anexo `1686` e `1830` (Anexo II, 2022).
   **Atenção:** o anexo `1686` tem CEP 88058-497, que é de **Ingleses**, e a
   rua da escola-mãe não consta no OSM. Esse conjunto é tratado apenas como
   variação de sensibilidade, não como parte do bairro.
5. **Convenções.** L = candidato de esquerda (Haddad 2018; Lula 2022 e 2026);
   R = adversário (Bolsonaro 2018/2022; Flávio Bolsonaro 2026); O = demais
   candidatos + brancos/nulos. "esq (L+R)/T" = polarização (votos nos dois
   principais candidatos / total). "Margem" = (L−R)/(L+R), em pontos
   percentuais (negativo = direita à frente). 2026 usa apenas o 1º turno
   (segundo turno ainda não realizado na data da coleta).
6. **Limitação de vinculação.** O número da seção é renumerado a cada eleição;
   seções de eleições diferentes foram casadas pelo `NR_LOCAL_VOTACAO`
   (escola) + número de seção quando coincidente.

## Resultados — bairro (núcleo: Muquém + Darcy Ribeiro)

| Eleição | Turno | Esquerda (L) | Direita (R) | Outros | Total | esq (L+R)/T | Margem (L−R)/(L+R) |
|---------|-------|-------------:|------------:|-------:|------:|------------:|-------------------:|
| 2018 | 1º | 305 | 919 | 692 | 1.916 | 63,9% | **−50,2 pp** |
| 2018 | 2º | 643 | 1.121 | 163 | 1.927 | 91,5% | **−27,1 pp** |
| 2022 | 1º | 1.338 | 1.206 | 356 | 2.900 | 87,7% | **+5,2 pp** |
| 2022 | 2º | 1.406 | 1.387 | 113 | 2.906 | 96,1% | **+0,7 pp** |
| 2026 | 1º | 2.217 | 2.611 | 779 | 5.607 | 86,1% | **−8,2 pp** |

Nota: o núcleo de 2018/2022 é apenas a EEB de Muquém (a Darcy Ribeiro não
existia como local de votação). 2018: Haddad × Bolsonaro. 2022: Lula ×
Bolsonaro. 2026: Lula × Flávio Bolsonaro.

### Sensibilidade — conjunto ampliado (núcleo + Intendente José Fernandes + anexos)

| Eleição | Turno | L | R | Outros | Total | esq (L+R)/T | Margem |
|---------|-------|---:|---:|-------:|------:|------------:|-------:|
| 2018 | 2º | 2.736 | 5.481 | 795 | 9.012 | 91,2% | −33,4 pp |
| 2022 | 2º | 5.021 | 6.056 | 442 | 11.519 | 96,2% | −9,3 pp |
| 2026 | 1º | 5.418 | 7.297 | 1.908 | 14.623 | 87,0% | −14,8 pp |

### Por escola (turnos decisivos)

| Escola | 2018 2ºT (L×R, margem) | 2022 2ºT (L×R, margem) | 2026 1ºT (L×R, margem) |
|--------|------------------------|------------------------|------------------------|
| EEB de Muquém | 643 × 1.121 (−27,1 pp) | 1.406 × 1.387 (+0,7 pp) | 1.393 × 1.777 (−12,1 pp) |
| EBM Darcy Ribeiro | — | — | 824 × 834 (−0,6 pp) |
| EEB Intendente José Fernandes (ext) | 1.676 × 3.443 (−34,5 pp) | 2.050 × 2.918 (−17,5 pp) | 1.584 × 2.666 (−25,5 pp) |

### Seções 2026 (núcleo) e "flips"

- 2026 1º turno, núcleo: **6 seções à esquerda × 14 à direita**
  (Muquém: 4 L / 9 R; Darcy Ribeiro: 2 L / 5 R). Bairro heterogêneo —
  detalhes em `detalhe_por_secao.csv`.
- Mesmo local + mesmo número de seção:
  - 2018 2ºT → 2022 2ºT: 2 flips, ambos para a esquerda
    (1503/seção 408 e 1686/seção 310).
  - 2022 2ºT → 2026 1ºT: 3 flips, todos para a direita
    (1503/408, 1686/310 e 1686/438) + 1 empate técnico (1686/447).

## Interpretação

- **2018:** bairro fortemente bolsonarista já no 1º turno (margem −50 pp);
  no 2º turno a direita consolidou com margem de −27 pp.
- **2022:** virada à esquerda — empate técnico (margem +0,7 pp no núcleo;
  +5,2 pp no 1º turno). A polarização atingiu o pico (96% dos votos em
  Lula × Bolsonaro).
- **2026:** retorno à direita, porém menos intenso que 2018 (−8,2 pp no
  núcleo, −12,1 pp na Muquém). A EBM Darcy Ribeiro, local novo, é praticamente
  paritária (−0,6 pp), o que explica a diferença entre o bairro e a Muquém.
- **Polarização (share L+R):** subiu de ~64% (2018 1ºT, com 692 "outros")
  para 86–96% em 2022/2026 — o eleitorado do bairro se consolidou em torno
  do eixo central da disputa.
- A escola Intendente José Fernandes (seção da zona 100, possivelmente
  Ingleses) mantém um perfil consistentemente mais de direita ao longo das
  três eleições (−34,5 / −17,5 / −25,5 pp).

## Ressalvas

1. A EBM Darcy Ribeiro só existe em 2026: a composição do "bairro" muda entre
   eleições (2026 soma +7 seções), o que afeta a comparabilidade.
2. A EEB Intendente José Fernandes e seus anexos podem não estar no Rio
   Vermelho (evidência aponta para Ingleses); usar o conjunto "ext" é
   sensibilidade, não estimativa do bairro.
3. Renumeração anual de seções: a comparação seção-a-seção entre eleições só
   é válida quando local + número coincidem.
4. 2026 está limitado ao 1º turno (segundo turno em 25/10/2026, posterior à
   coleta).
5. Bairro inferido por geocodificação de endereços de escolas (OSM/Nominatim +
   faixa de CEP 88060-xxx); não há campo de bairro nos dados do TSE.

## Arquivos

- `comparativo_1o_turno.md` — comparação direta dos 1º turnos (2018/2022/
  2026): tabelas bairro núcleo e da mesma escola, detalhamento por candidato,
  leitura e ressalvas.
- `detalhe_por_secao.csv` — 187 linhas: ano, turno, local, zona, seção, L, R,
  outros, total e índices (esquerda × direita), para todas as seções do núcleo
  e do conjunto ampliado nas três eleições.
- Origem bruta: `../eleicoes-2018/`, `../eleicoes-2022/`, `../eleicoes-2026/`
  (arquivos `votacao_secao_*_BR.csv` do TSE; presidente apenas nos arquivos
  `BR`).
