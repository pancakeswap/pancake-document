# Translation glossaries

**English is the single source of truth.** Each supported language has its own
glossary file in this directory, named after its branch:

```
glossaries/
  README.md          ← this file (shared conventions + keep-in-English list)
  chinese.md         ← Chinese (Simplified)
  spanish.md         ← (add when first translating espanol)
  japanese.md        ← (add when first translating japanese)
  ...
```

## Format

Each `<language>.md` is a two-column table mapping the **English source term** to its
translation in that language. The English column is canonical and identical across all
languages; only the translation column differs. This keeps the languages decoupled —
editing one glossary never touches another.

```markdown
| English (source of truth) | <Language> |
|---------------------------|------------|
| Swap                      | 兑换        |
| Liquidity                 | 流动性      |
```

A glossary may also declare a per-language **register/style** note (e.g. Chinese uses the
informal 你).

## Keep-in-English (all languages)

These are **not** translated in any language — brand/product names, versioned product
names, and acronyms. Do not add them to per-language glossaries:

- Brand/product: PancakeSwap, MEV Guard, Social Login, Pancake Gifts, Smart Router,
  StableSwap, Hooks, veCAKE, bCAKE, iCAKE, CAKE, CAKE.PAD, WBETH, SnBNB.
- Versioned product names: PancakeSwap Infinity, PancakeSwap X, Tokenomics 3.0, v3/v2.
- Acronyms: MEV, RPC, FAQ, APR, ROI, IL, IFO, TWAP, ALP, AMM, CLAMM, LBAMM, RWA, BSC, CEX.

## Adding a language

Copy the table header from an existing glossary, translate the right column, add any
register note, and reference it from the run — no other files change.
