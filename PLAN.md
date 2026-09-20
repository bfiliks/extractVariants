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

- [x] Parse the Fascicle 34 documentation (currently prose in a `.docx`) into structured records: poem, sheet, base text, variant(s), position, the team's own category judgments where stated. Done 2026-09-20 — `data/fascicle34_hand_coding.json`, parsed directly from the source table's own XML structure (not re-typed from the flattened text), all 17 poems, spot-checked against the original for accuracy.
- [ ] For each base-text/variant pair, classify it against the paper's own two-level taxonomy using an LLM, blind to the team's original coding.
- [ ] Measure agreement between the 2023 hand-coding and the computational pass — where they agree, where they don't, and *why* the disagreements happen (this is the actual finding, not a score to optimize).
- [ ] Write this up as the results section the 2023 paper draft never had.

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
