# Testing the founding hypothesis: can the taxonomy be applied computationally?

**Method.** The team's own worked example (16 base-text/variant pairs from two Fascicle 34 poems, each hand-assigned a category in 2022) was used as ground truth. A fresh, isolated LLM instance — with no access to this project's conversation history or the team's actual answers — was given only: the base text, the variant, its part of speech, and the paper's own two-level taxonomy definitions, quoted verbatim. It classified all 16 pairs blind. Its answers were compared against the team's 2022 labels only afterward.

**Headline finding: the taxonomy's five formal categories don't cover the team's own dominant real-world judgment.** The team used five category labels in practice — Successive, Amplification, Additive, Substitutive, Extensive — but the paper's stated Level-1 taxonomy only defines five *different* categories: repetitives, amplifiers, antithesis, additions, uncategorized. Only one of the team's five labels ("Amplification") maps directly onto a defined category ("amplifiers"). The other four don't:

| Team's applied label | Count (of 16) | Formal taxonomy category it should map to | Actually defined in the paper? |
|---|---|---|---|
| Substitutive | 9 (56%) | — | **No.** Not one of the five defined categories. |
| Successive | 2 | "additions" (the paper's own text calls additions that "follow the base text without interruption" *successives*) | Named only as a sub-case inside "additions," not its own category |
| Additive | 2 | "additions" | Yes, but under a different label |
| Amplification | 2 | "amplifiers" | Yes |
| Extensive | 1 | — | **No.** Not defined anywhere. |

**"Substitutive" — one word or phrase offered as a direct alternative to another — is the single most common real relationship in the data (9 of 16 pairs, more than all other categories combined), and it has no defined category in the theory at all.** The founding taxonomy was built reasoning qualitatively about a handful of examples; applying it to real data immediately surfaces that its most basic, common case — plain substitution — was never actually named as a category. That's not a computational failure. It's a real finding about the theory itself, the kind only surfaced by trying to apply it systematically rather than reasoning about it in the abstract.

**Where the formal categories do exist, human and computational judgment still diverge — genuinely, not just terminologically.** Two clear cases:

- **"rectified" → "qualified"** (poem 2). The team's own 2022 notes reasoned that "qualified" *extends* the meaning of "rectified" — hence the invented label "Extensive." Classifying blind against only the formal taxonomy, the isolated agent called this **antithesis**: "rectified" implies restoring correctness, "qualified" implies limitation — opposing senses of completeness. Same pair, same available theory, two substantively different readings. This is a live interpretive disagreement, not a scoring artifact.
- **"who dare" → "allowed"** (poem 2). The team called this **Amplification**. The agent called it **antithesis** — dare locates agency in the self, "allowed" relocates it to external permission, an opposition in *where agency sits*, not a matter of degree.

**One unplanned convergence worth noting.** Classifying blind, the agent independently reached for the word "successive" to describe "but been" → "been one" ("reads as a successive completion... rather than a true substitute reading") — the team's own word, but applied to a *different* pair than the two the team used it for. The concept is clearly salient to both human and computational readers; which specific pairs it gets attached to isn't yet consistent between them.

**What this settles, and what it doesn't.** The founding question from 2022 — *can this be done computationally, even without the skillset at the time* — gets a real, evidenced yes: a taxonomy defined in prose can be applied consistently to real base-text/variant pairs by a computational process, blind, with legible reasoning for every call. What it doesn't settle, and shouldn't be forced to settle, is *which* reading is correct where team and computation disagree — that's the actual textual-studies question ("do we choose one variant or the other for the base text") the project set out to explore, and this result sharpens it rather than closing it: the disagreements aren't noise, they're readings that now have to be argued for, on both sides.

**Next revision this suggests for the taxonomy itself:** add "substitutive" as a defined Level-1 category (it's the most common relationship in the data and currently undocumented), and decide explicitly whether "successive" is a synonym for "additions" or a distinct category — the theory text and the applied coding currently disagree with each other on this, not just with the computational pass.
