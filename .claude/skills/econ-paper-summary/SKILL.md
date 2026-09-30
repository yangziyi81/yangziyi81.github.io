---
name: econ-paper-summary
description: Summarize economics papers (PDFs, NBER/SSRN/journal links, or titles) into a fixed IO × environmental-economics template, and keep a running literature table. Use when the user asks to summarize, compare, or log a paper or working paper, or to see what a researcher has been working on lately.
---

# Econ paper summary

The user is an economics PhD student working in industrial organization (IO) and environmental/energy economics. Summaries should help them (1) understand a paper quickly, (2) place it relative to their own research, and (3) reuse it in slides and literature reviews.

## Inputs

- **PDF path** → read the full text (use the `pdf` skill if extraction is needed). Read the introduction, data, identification/model, results and conclusion. Don't summarize from the abstract alone.
- **URL** (NBER, SSRN, CEPR, journal page, author website) → fetch it. If only an abstract is reachable, say so in the summary and mark those fields "abstract only".
- **Title or author name only** → search for it first. For a researcher ("what is X working on"), find their personal or faculty website and list their newest working papers, then summarize each.

## Verification rules (non-negotiable)

- Every paper must come with a URL that you actually opened or saw in search results.
- Never invent authors, venues, years, numbers or findings. If you're not sure of something, write `UNVERIFIED` next to it.
- Record status precisely: `Published: <journal, year>`, `Forthcoming: <journal>`, `Working paper: <series and number, date of latest version>`. Say "R&R" only if the author's site says so.
- Copy key numbers (elasticities, pass-through rates, welfare effects) exactly as the paper reports them, with units.

## Output template (one per paper)

```markdown
### <Title> — <Authors> (<Year>)
**Status:** <published / forthcoming / WP series + number> · **Link:** <url>
**Field tags:** <e.g., IO; environmental; electricity; structural>

- **Question:** one sentence.
- **Why it matters:** the policy or economic stakes, one or two sentences.
- **Setting & data:** industry, geography, period, data sources and unit of observation.
- **Method:** structural (which model: demand system, supply/conduct, dynamic game, auction, etc.) or reduced-form (DiD, RD, IV, event study, bunching…). Name the identifying variation.
- **Key findings:** 2–4 bullets with the paper's own numbers.
- **Counterfactuals / policy simulations:** if any.
- **Contribution vs. prior work:** which strand(s) it advances and the 1–3 closest papers.
- **Limitations / open questions:** what it can't answer; natural extensions.
- **Relevance to my work:** how it could be used as motivation, a benchmark, a method, or a data source. Ask the user about their project if you don't know it.
```

## Multiple papers

After the individual summaries, add:

1. **Literature table** (markdown), one row per paper, with columns:
   `Authors | Year | Venue/Status | Setting | Method | Key finding | Link`
2. **Synthesis:** 3–5 bullets on the shared themes, where papers disagree, and the gaps.
3. **Slide-ready line:** one sentence per paper, short enough for a "related literature" slide.

## Saving

If the user wants a running log, add summaries to `literature/summaries.md` and table rows to `literature/lit_table.md` in the working directory, creating them if needed. Don't duplicate a paper that's already logged: update its entry instead (for example, when a working paper gets published).
