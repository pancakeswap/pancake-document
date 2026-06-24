---
name: translate-language
description: Translate the PancakeSwap GitBook docs into one supported language, using the `en` branch as the source of truth. Use when asked to translate/update docs for a language (e.g. "translate the docs into Chinese", "update the Spanish translation", "translate the Trade section into Japanese"). Orchestrates per-language translation subagents and opens a PR into the language branch.
---

# Translate docs into one language

This repo is a **GitBook** project. Translations are **branch-based**: each language
lives in its own git branch (not a `/locale/` folder). The English branch `en` is the
**single source of truth**; every other branch is a translation that drifts behind it.

Your job: bring a target language branch closer to `en` by translating the requested
scope, and open a PR into that language branch.

## Inputs

- **Target language** (required) — e.g. `chinese`. Maps to a branch name (see below).
- **Scope** (optional) — a section (e.g. "Trading Tools"), a list of pages, or "all
  missing pages". If unspecified, ask the user whether to do one section (pilot) or the
  full gap. Default to a single named section for a first run.

## Supported language branches

`git ls-remote --heads origin` is the authority. Known translation branches:

| Branch | Language |
|--------|----------|
| `chinese` | Chinese (Simplified) |
| `espanol` | Spanish |
| `french` | French |
| `indonesian` | Indonesian |
| `italian` | Italian |
| `japanese` | Japanese |
| `portuguese-brazilian` | Portuguese (BR) |
| `russian` | Russian |
| `turkish` | Turkish |
| `vietnamese` | Vietnamese |
| `dach` | German (partial) |

`en` is the source. `en_bkup` is a backup — never target it.

## Procedure

### 1. List supported languages & confirm target
- `git fetch origin en <target-branch>`
- Confirm the target branch exists in the table above (or via `git ls-remote --heads origin`).
- Run `git log -1 --format='%ci' origin/en` and `origin/<target>` to report how stale the
  translation is.

### 2. Set up the working branch
- Create the dev branch **off the target language branch** (so the PR diffs against it):
  `git checkout -B <work-branch> origin/<target-branch>`
- Determine the scope's English source files from `origin/en` (use `SUMMARY.md` and the
  directory tree). Compare the `en` and target `SUMMARY.md` to find pages with no
  translated counterpart.

### 3. Per-section translation subagents
For the chosen scope, materialize the English source files into the working tree
(`git checkout origin/en -- <path>/`), then **spawn one translation subagent per
coherent sub-area** (run them in parallel). Each subagent:
1. Translates the assigned `.md` files **in place** into the target language.
2. **Handles images** — see the IMAGE POLICY below. This is the most common gap.
3. Follows the TRANSLATION POLICY checklist below.

Give every translation subagent the policy + glossary in its prompt.

### 4. Update SUMMARY.md (mirror the en IA)
Add the new/updated entries to the target branch's `SUMMARY.md`, mirroring the **current
English information architecture** (same section grouping and same `path/to/file.md`
paths as `en`), but with **translated titles**. Keep emojis. **Mandatory:** when the
English docs use new directory paths that the language branch's SUMMARY does not yet
reference (a path migration, e.g. legacy `chan-pin/`/`products/` → `trade/`/`earn/`), the
SUMMARY.md update must ship in the **same PR** — never leave new pages unlinked or the
nav pointing at old paths.

### 5. Copy referenced image assets  ⚠️ critical
GitBook image refs point at `.gitbook/assets/<file>` relative to repo root. These binary
assets exist on `en` but are usually **absent on the language branch**, so images render
broken/omitted. After translating, scan every translated file for `.gitbook/assets/...`
references and `git checkout origin/en -- "<asset>"` for any that are missing on the
target branch. (Filenames often contain spaces and parentheses — quote them. Watch for
`Screenshot ...png` names and filenames containing a **U+202F narrow no-break space**
before AM/PM — match the exact bytes, not a regular space.)

### 6. Commit & open PR
- Commit translations and assets (separate, clearly-described commits are fine).
- Push the work branch.
- Open a PR with **base = the target language branch** (NOT `en`, NOT the repo default).
- PR body: scope, conventions applied, and a note that a **native-speaker review** is
  recommended before merge.
- Do not merge. If git push is blocked (403) in this environment, retry; the GitHub MCP
  branch/PR tools may have write access even when raw git does not.

## TRANSLATION POLICY (rules every translation subagent must follow)

- **P1 Frontmatter** — keep `---` delimiters and YAML keys; translate only natural-language
  values (e.g. `description:`). Never translate keys like `icon:`.
- **P2 Structure** — preserve heading levels, list nesting, tables, blockquotes, and
  GitBook blocks (`{% hint %}`, `{% tabs %}`, `<figure>`, `<table>`).
- **P3 Links & paths** — never alter URLs, relative link targets, or anchors. Translate
  only human-readable link text.
- **P4 Images present** — every image reference in the `en` source must exist in the
  translation, **and** the referenced `.gitbook/assets/<file>` must be included in the
  branch (copied from `en` if missing). No broken/omitted images.
- **P5 Brand/terms** — keep product/brand names in English (PancakeSwap, MEV Guard,
  Social Login, Pancake Gifts, veCAKE, CAKE, etc.) and keep acronyms (MEV, RPC, FAQ, APR,
  IFO, TWAP) as-is. This includes **versioned upgrade names** — e.g. "Tokenomics 3.0",
  "PancakeSwap Infinity", "v3/v2" — keep the English product name even when surrounding
  descriptive words are translated.
- **P6 Inline tokens** — never change HTML entities (`&#x20;`), code spans/blocks, or
  placeholders (e.g. `{Gift_Code}`).
- **P7 Emojis** — preserve emojis in headings and titles.
- **P8 SUMMARY** — new pages added under the correct section mirroring the en IA; titles
  translated; file paths identical to `en`; no dangling links. The SUMMARY nav title
  should be consistent with the page's translated H1 (the P5 acronym exception applies —
  e.g. "FAQ" in nav vs "常见问题解答" in the H1 is acceptable).
- **P9 Completeness** — no untranslated English prose left behind (other than the allowed
  brand/technical terms in P5).
- **P10 Glossary & register** — apply the target language's glossary consistently. Each
  language has its own glossary file under `glossaries/<language>.md`, keyed to the
  English source term (see `glossaries/README.md`); follow its register note too.

## Glossaries

Glossaries live in `glossaries/`, one file per language, each keyed to the **English
source of truth** (`glossaries/README.md` holds the shared keep-in-English list of brand
names, versioned product names, and acronyms). Before translating, load the target
language's glossary (e.g. `glossaries/chinese.md`) and pass it to every translation
subagent. When you settle a new term during a run, add it to that language's glossary
file only — never edit another language's file.

