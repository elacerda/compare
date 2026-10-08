# Rio Vermelho + Ingleses (Norte de Florianópolis/SC) — polarização eleitoral 2018–2026

Análise **conjunta** da corrida presidencial (esquerda × direita) nas seções dos
bairros **Rio Vermelho** e **Ingleses**, Florianópolis (SC), para as eleições de
**2018** (Haddad × Bolsonaro), **2022** (Lula × Bolsonaro) e **2026** (Lula ×
Flávio Bolsonaro). Os dois bairros foram mapeados juntos e extraídos numa
**execução única**: **11 locais, zona 100, 525 seções** (2018/2022/2026).

Dados: arquivos oficiais do TSE, em `../eleicoes-{2018,2022,2026}/`.

> **Rerun 2026-10-08 (pipeline v2 da skill `flip-flavio-lula`)**: regressão
> exata contra os valores antigos; validação `T == QT_COMPARECIMENTO` OK em
> 525/525 seções; `aptos >= T` OK.

## Como ler esta pasta

| Arquivo | Conteúdo |
|---|---|
| `README.md` (este) | visão regional: conjuntos, números-chave, arquivos da execução |
| `README-riverio-v.md` | Rio Vermelho: metodologia do bairro, resultados por conjunto, flips, interpretação, ressalvas |
| `README-ingleses.md` | Ingleses: metodologia do bairro (47 locais geocodificados, exclusões), resultados, flips, interpretação, ressalvas |
| `estrategia-flip-norte-floripa.md` | estratégia de 2º turno: perfis, incoerências dos planos (com páginas), cartões, alvo por seção |
| `detalhe_por_secao.csv` | 525 linhas, 18 colunas — todas as seções dos 11 locais, 3 eleições |
| `config.json`, `config_aptos.json`, `conjuntos.json`, `nomes.json` | execução conjunta (11 locais, 4 conjuntos) — reprodutível com 03/04/05 da skill |
| `comparativo_1o_turno.md` | artefato histórico (fluxo anterior, detalhamento por candidato) |

## Conjuntos (`conjuntos.json`)

- `RV-NÚCLEO`: `1503` (EEB de Muquém), `1929` (EBM Darcy Ribeiro — só 2026)
- `RV-SENS`: núcleo + `1368` (EEB Intendente José Fernandes), `1686` (anexo),
  `1830` (Anexo II — só 2022)
- `ING-NÚCLEO`: `1562`, `1600`, `1732`, `1376`, `1643`, `1678`, `1686`
  (93 seções, 34.882 aptos em 2026)
- `ING-SENS`: `ING-NÚCLEO` + `1368` (fronteira)

**Atenção (double counting):** `1368` é a fronteira Rio Vermelho × Ingleses e
`1686` (anexo, CEP 88058) está em `ING-NÚCLEO` **e** em `RV-SENS`. Ao combinar
os dois bairros, contar 1368 uma vez (região = `RV-NÚCLEO` + `ING-NÚCLEO` +
`1368` + `1830`).

## Números-chave — 2026 1º turno (margem = (L−R)/(L+R))

| Conjunto | L × R | Total | Margem |
|---|---|---:|---:|
| RV-NÚCLEO | 2.217 × 2.611 | 5.607 | **−8,2 pp** |
| RV-SENS | 5.418 × 7.297 | 14.623 | −14,8 pp |
| ING-NÚCLEO | 9.280 × 13.548 | 26.099 | −18,7 pp |
| ING-SENS | 10.864 × 16.214 | 30.942 | −19,8 pp |

Tabelas completas (os 5 turnos por conjunto, decomposição de "Outros",
matemática do 2º turno por conjunto, flips com cobertura de matching): nos dois
READMEs de bairro.

## Estratégia de 2º turno

`estrategia-flip-norte-floripa.md` — objetivo realista do território:
**+2.000 a +2.500 no diferencial L×R** (virar o núcleo de Rio Vermelho, +394 a
+500; devolver 1678/Capivari à esquerda como em 2022; converter a zona das 22
seções próximas em Ingleses, +365 no teto; estancar 1686/1732; comparecimento
de indecisos). Vencer a região inteira (~18 pp de swing) está fora de alcance.
