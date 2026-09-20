# Project plan: continuing ExtractV from 2023

**Status as of 2026-09-20:** This project went dormant after 2023 — the paper ("World, Selves, and Sun: A Computational Approach to Emily Dickinson's Variants") was never submitted, the ExtractV model was never built past a pipeline diagram, and the human-computation model gestured at on the Scalar site was never operationalized. Twelve internal working documents (abstracts, meeting notes, the full paper draft, conference slides, the Fascicle 34 hand-coding) existed only in a local Downloads folder, disconnected from both the GitHub repo and the published Scalar site. This plan is the first time the four live threads have been named in one place since then.

## 1. Where this stands

- **Live artifacts**: GitHub repo (`bfiliks/extractVariants`, public, visualization code + data) and a Scalar book (`ctsdh.org/dickinsonviz`, the full scholarly presentation — About, Conceptualizing Variants, Computational Approach, Data Visualizations, Contributions, Acknowledgements). The two now link to each other both ways.
- **Team**: Felix Oke, Samantha Chipman, and Ria De (all Loyola University Chicago at the time), advised by Marta Werner. Presented at STS 2023 (The New School) and prepared for ESTS. Credit for all three is now correct in both the repo README and the Scalar Acknowledgements page.
- **Real, unpublished data**: hand-coding of 17 poems in Fascicle 34 (poem, sheet, variant list, position/scale notes, observations, open questions per poem) — done by hand across the team, currently sitting only in a `.docx`, in prose form, never turned into structured data.
- **Real, unfinished theory**: a two-level variant taxonomy (repetitive / amplifier / antithesis / addition / uncategorized, crossed with exclusive / non-exclusive alternatives), plus experimental categories (meandering, molecularization, and others named only in the conference slides) that were never tested against real data at scale — only reasoned about qualitatively on a handful of poems.
- **The founding question, stated plainly by Felix**: looking at Franklin's *Variorum* manuscripts, (1) can Dickinson's variants be traced at all — answered yes, by hand, via the Fascicle 34 coding; (2) can that be done computationally — answered yes *on faith*, before the team had the skillset to actually build it.

## 2. Active work: testing the founding hypothesis for real

The one piece of "ExtractV" that's newly tractable, now that the skillset exists: **run computational classification against the team's own 2022 hand-coding, as a validation study**, not a replacement for it.

- [x] **Done and complete, 2026-09-20**, after four rounds (three partial, kept in `data/` as the record of how this developed; the fourth complete and authoritative). Final state:
  - **Data**: `data/fascicle34_authoritative.json` — Franklin's full critical apparatus for all 17 Fascicle 34 poems, pulled directly from the live Emily Dickinson Archive (Harvard/Amherst) manifests, not this project's own 2022 scrape or any secondary text. 72 base-text/variant relationships (84 flattened). Three poems (8, 10, 15) confirmed variant-free, matching the team's own 2022 notes. Used under EDA's CC BY-NC-ND 3.0 terms, non-commercial-research provision; kept out of this repo except as short phrase-pairs.
  - **Classification**: `data/fascicle34_final_classification.json` — all 84 pairs classified against the paper's own taxonomy, blind, in three independent batches.
  - **Write-up**: `results_fascicle34_classification.md`, rewritten once as a single clean account rather than three patched sections.
  - **Founding hypothesis**: confirmed — the taxonomy can be applied consistently to the complete manuscript record, not just a fragment of it.
  - **The taxonomy's real gap**: "Substitutive" (plain word-for-word substitution) has no defined category, and shows up in every single test run (56%, 33%, 32%, 14% across four independent passes) — but its *exact size is unstable*, not a fixed number, most likely because later runs offered "Uncategorized" as an explicit competing option. Reported as an honest range and a methodological limitation, not rounded to one convenient percentage.
  - **Corrections made along the way, not hidden**: two errors from pre-manuscript-access reconstruction (poem 3's Curricle/Vehicle direction; poem 6's Would/Could misread as should/could), one retraction that was itself wrong (poem 11's Root→Core, retracted in round 3, restored once Harvard's live record confirmed it was real), and one overclaim corrected after direct feedback (calling missing markup an "EDA archive gap" when it was this project's own 2022 scrape that was incomplete — EDA's own encoding goals explicitly include capturing variants).

## 3. Other directions — logged, not dropped

Explicitly kept on record per Felix's instruction not to lose sight of these while §2 is active:

- **Variant Concordance dataset.** Turn the Fascicle 34 hand-coding into a real, structured, published dataset (JSON/CSV) plus a small static browse tool — the same no-backend architecture as `printers-file-search`. Finishable independent of §2; arguably §2's own data prerequisite either way.
- **Make the irresolution legible, don't resolve it.** The scholarship's real open question — does a reader choose one variant over another, or hold both open — is a live textual-studies debate, not an engineering problem. A tool that surfaces *where* the ambiguity is and *what kind* it is (per the taxonomy) is the honest computational contribution; forcing a single "resolved" reading would misrepresent the scholarship.
- **A dictionary-like resource, EDA-style.** Structuring Webster's 1844 sense-entries used in the variant-alignment examples (e.g., "power" vs. "art") as queryable data of its own, reusable beyond this one project.
- **Publication.** The existing paper draft has an abstract, full theory section, taxonomy, and bibliography — it needs the results section §2 would supply, not a rewrite. Chipman, De, and Werner's contributions stay credited exactly as they were in 2022–23, regardless of who finishes the computational half now.

## 4. Sustainability, honestly

- **One active maintainer right now** (Felix), same as every other project in this practice — named explicitly rather than assumed.
- **Original collaborators should be looped in before anything gets published or substantially changed publicly** — Chipman and De contributed real intellectual work (the taxonomy, the theory framing, half the hand-coding) that this plan builds on directly; continuing solo on the computational half doesn't change whose ideas they are.
- **Scope discipline**: the 2022 vision (Neo4j graph DB, a public API, a full NLP pipeline with custom collation) was too large for a small team then and is still a multi-year scope now. §2 is deliberately small enough to actually finish.
