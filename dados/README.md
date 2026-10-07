# Dados oficiais de eleições do TSE — resultados por seção

Arquivos oficiais baixados em **2026-10-06** do Portal de Dados Abertos do TSE
(`dadosabertos.tse.jus.br`) e do CDN `cdn.tse.jus.br`. Cobrem as Eleições Gerais
de **2026 (1º turno)**, **2022 (1º e 2º turnos)** e **2018 (1º e 2º turnos)**,
com resultados **por seção eleitoral**. Total: ~56 GB.

## Estrutura

```
dados/
├── eleicoes-2026/   # 1º turno (04/10/2026)
├── eleicoes-2022/   # 1º turno (02/10/2022) + 2º turno (30/10/2022)
└── eleicoes-2018/   # 1º turno (07/10/2018) + 2º turno (28/10/2018)
```

Cada pasta contém:

| Arquivo | Conteúdo |
|---|---|
| `votacao_secao_<ANO>_BR.csv` (+ `.zip`) | Votos **por candidato e por seção**, cargo **Presidente**, todas as UFs. Em 2022/2018 inclui 1º e 2º turno (coluna `NR_TURNO`). |
| `zips/votacao_secao_<ANO>_<UF>.zip` | Votos por candidato e seção para **todos os cargos** (Governador, Senador, Dep. Federal e Estadual) de cada UF. 2022/2018: 2º turno de governador apenas nas UFs que tiveram 2º turno (ver abaixo). |
| `detalhe_votacao_secao_<ANO>_*.csv` | Detalhe da apuração **por seção e por cargo**: aptos, comparecimento, abstenções, votos nominais/brancos/nulos/de legenda, status da seção, modelo de urna. |

Detalhamentos por ano (incluem URLs originais e notas específicas):
`eleicoes-2026/README.md`, `eleicoes-2022/README.md`, `eleicoes-2018/README.md`.

## Cobertura de 2º turno (governador)

- **2022**: AL, AM, BA, ES, MS, PB, PE, RO, RS, SC, SE, SP
- **2018**: AM, AP, DF, MG, MS, PA, RJ, RN, RO, RR, RS, SC, SE, SP

O 2º turno da **presidência** está nos arquivos `..._BR.*` (ambos os anos).
2026 tem apenas 1º turno até o momento.

## Formato dos CSV

- Separador `;`, campos entre aspas `""`, codificação **latin-1 (ISO-8859-1)**, 26 colunas.
- Colunas principais: `SG_UF`, `CD_MUNICIPIO`/`NM_MUNICIPIO`, `NR_ZONA`, `NR_SECAO`,
  `CD_CARGO`/`DS_CARGO`, `NR_VOTAVEL` (nº do candidato), `NM_VOTAVEL`, `QT_VOTOS`,
  `NR_LOCAL_VOTACAO` (nº da seção), `NM_LOCAL_VOTACAO`, `DS_LOCAL_VOTACAO_ENDERECO`;
  em `detalhe`: `QT_APTOS`, `QT_COMPARECIMENTO`, `QT_ABSTENCOES`, `QT_VOTOS_*`,
  `ST_SECAO_INSTALADA`, `ST_SECAO_ANULADA`, `CD_MODELO_URNA`.
- Diferença entre anos: em **2018** os numéricos vêm sem aspas; em **2022/2026**
  todos os campos vêm entre aspas. Remover aspas antes de usar.
- Votos brancos/nulos aparecem como "candidatos" (`VOTO BRANCO`, `VOTO NULO`).

## Observações / armadilhas

- O zip **RR-2022** inclui também a Eleição Suplementar de Governador de RR (2026);
  o zip **MT-2018** inclui a Suplementar de Senador de MT (2020); o DF-2022 inclui a
  "Eleição Conselho Distrital 2022". Filtrar por `DS_ELEICAO`/`DT_ELEICAO`.
- `DS_ELEICAO` tem variações de caixa entre arquivos ("ELEIÇÃO GERAL FEDERAL 2022"
  vs "Eleições Gerais Estaduais 2022").
- Exterior aparece como UF `ZZ` (presente em 2026 e 2018; ausente no detalhe de 2022).
- ~499 mil seções em 2026 (incl. exterior); menos em 2022/2018.

## Integridade e validação

- Cada pasta tem `MANIFEST.sha256` com os checksums de todos os zips
  (validados também com `unzip -t` na hora do download).
- Totais presidenciais recalculados a partir das seções **batem com os números
  oficiais do TSE**:

| Eleição | Turno | Resultados (votos) |
|---|---|---|
| 2026 | 1T | Flávio Bolsonaro 56.104.503 · Lula 53.879.538 · Cury 3.448.569 · Renan Santos 2.675.887 · Caiado 2.605.148 · Zema 326.488 · nulos 3.669.003 · brancos 2.300.798 |
| 2022 | 1T | Lula 57.259.504 · Bolsonaro 51.072.345 · Tebet 4.915.423 · Ciro 3.599.287 · Boulos 559.708 · nulos 3.487.874 · brancos 1.964.779 |
| 2022 | 2T | Lula 60.345.999 · Bolsonaro 58.206.354 · nulos 3.930.765 · brancos 1.769.678 |
| 2018 | 1T | Bolsonaro 49.277.010 · Haddad 31.342.051 · Ciro 13.344.371 · Alckmin 5.096.350 · Marina 1.069.578 · nulos 7.206.222 · brancos 3.106.937 |
| 2018 | 2T | Bolsonaro 57.797.847 · Haddad 47.040.906 · nulos 8.608.105 · brancos 2.486.593 |

## Fontes

- Dataset CKAN: `https://dadosabertos.tse.jus.br/dataset/resultados-<ANO>`
- Padrão de URLs:
  `https://cdn.tse.jus.br/estatistica/sead/odsele/votacao_secao/votacao_secao_<ANO>_<UF|BR>.zip`
  `https://cdn.tse.jus.br/estatistica/sead/odsele/detalhe_votacao_secao/detalhe_votacao_secao_<ANO>.zip`
- 2026: relatório oficial em PDF — `eleicoes-2026/Relatorio_Resultado_Totalizacao_2026_BR.zip`
