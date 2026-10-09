# Planos de governo — texto extraído (fonte única para as análises)

Texto página a página dos dois planos, extraído com `06_planos.py` da skill
`flip-flavio-lula`. **Todas as análises (`analise_*/`) usam estes txts**; não
recriar por análise.

| Arquivo | Plano | PDF de origem (raiz do repo) | Páginas |
|---|---|---|---:|
| `flavio.txt` | Flávio (PL) — "Para o Brasil Vencer o Atraso" | `FLAVIO-BOLSONARO-PARA-O-BRASIL-VENCER-O-ATRASO.pdf` | 76 |
| `lula.txt` | Lula (PT) — "Diretrizes para o Programa de Transformação do Brasil" | `Programa-Governo-LULA-2026.pdf` | 84 |

- Marcador de página: `=== PAGINA N ===` (N = página do PDF oficial; as
  citações das estratégias usam essa numeração).
- Extraído em **2026-10-09** com `pypdf 6.19.0`.

## SHA-256 dos PDFs (confira antes de reexporar)

- `FLAVIO-BOLSONARO-PARA-O-BRASIL-VENCER-O-ATRASO.pdf`:
  `ff60b7ae45083471448af7fa0bf62bbe7ce209a1d21682b3482f142e0cb8b4f0`
- `Programa-Governo-LULA-2026.pdf`:
  `75e2dab7b9af27454a5c1a44c3bb0d7e0eaddbd1c355ccf1536f0d0be927e47b`

Se o hash do PDF mudar, reextrair:

```
python3 scripts/06_planos.py FLAVIO-...pdf Programa-...pdf \
    --out dados/planos/ --nomes "Flavio,Lula"
```

e atualizar as datas/hases acima.
