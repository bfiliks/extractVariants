# Testing the founding hypothesis, on the complete data

*This document was rewritten once, deliberately, once a complete authoritative source (Harvard's own Emily Dickinson Archive manifests) replaced the partial reconstructions of three earlier rounds. Those rounds' own data files are kept in `data/` as the record of what was known at each stage — including two real errors and one premature retraction, corrected here rather than hidden. This is the final, single account of what those rounds converged toward.*

## The question

In 2022, looking at Franklin's *Variorum* facsimiles of Dickinson's actual manuscripts — words in the margins, words below the poem, crossed out and offered again — the team asked two questions: can Dickinson's variants be traced systematically at all (yes, proven by hand, poem by poem, in the team's own Fascicle 34 documentation), and can that tracing be done computationally, even without the skillset to build it yet (answered yes, on faith, in 2022). This is that second answer, tested for real.

## The data

**All 17 poems of Fascicle 34, all of Franklin's documented variant readings** — 72 distinct base-text/variant relationships (84 once poems with more than one variant per base word are counted separately) — pulled directly from the Emily Dickinson Archive's own critical apparatus, published live at Harvard's CURIOSity platform (`data/fascicle34_authoritative.json`). Three poems (8, 10, 15) are confirmed to have no variants at all, exactly matching the team's own 2022 field notes. Four poems exist in more than one manuscript copy, and where Dickinson's copies genuinely diverge in wording — not just in the alternates offered, but in the base text itself — both readings are kept distinct, not merged.

This is a correction of three earlier, partial attempts, not a supplement to them:

- **Round 1** used only the team's own 16-pair worked example (the two poems they'd applied their taxonomy to directly).
- **Round 2** reconstructed 9 more pairs from published reading-edition text, before manuscript access.
- **Round 3** used this project's own 2022 scrape of the archive's TEI files — better than reading editions, but itself incomplete: it missed real variants in at least three poems, and one of its own conclusions (retracting "Root"→"Core" as unconfirmed) turned out to be wrong once checked against Harvard's live record, which confirms the pair is real. The local scrape had simply missed it too.

Used under the Emily Dickinson Archive's own Copyright & Terms of Use (CC BY-NC-ND 3.0, credit to the owning institution — Amherst College / Houghton Library, Harvard — required); only short phrase-pairs are committed to this repository, never full transcriptions or images, consistent with that license and with what non-commercial scholarly use requires.

## Finding 1: the founding hypothesis holds

All 84 pairs were classified against the paper's own two-level taxonomy by agent instances with no access to any team-assigned label (none exist for 82 of the 84 pairs — the team never formally categorized most of Fascicle 34) and no access to each other's work. The taxonomy, defined in prose in 2022, can be applied consistently and legibly to real manuscript data. That's a real yes to the founding question, on the complete dataset this time, not a fragment of it.

## Finding 2: the taxonomy has a real, replicated gap — but its exact size is unstable

Across the classification distribution (n=84): **Repetitives 25 (30%), Amplifiers 21 (25%), Antithesis 18 (21%), "Substitutive" 12 (14%), Uncategorized 6 (7%), Additions 2 (2%).**

"Substitutive" — plain, roughly equal-status word-for-word substitution — is not one of the paper's five defined Level-1 categories at all. It shows up anyway, every time this has been tested: 56% of round 1's 16 team-labeled pairs, 33% of round 2's 9, 32% of round 3's 31, and 14% of this final run's 84. Four independent classification passes, and the taxonomy's gap never disappears — but the size of that gap moved by a factor of four depending on which run you look at.

**That instability is itself the more honest finding, and it would have been easy to bury.** The most likely cause: this run's prompt explicitly offered "Uncategorized" as a standing option in the same list as "Substitutive (undefined)," and a meaningful share of pairs that earlier runs defaulted to "Substitutive" landed in "Uncategorized" instead here (6 pairs, 7%) — two different ways of saying the same thing, "this doesn't fit," competing for the same cases. A single pair makes this concrete: "souls"→"Sun" (poem 1) was called an amplifier in round 1's blind classification; the same pair, same taxonomy, a different independent run, called it "Uncategorized" here. **The taxonomy's gap around plain substitution is real and reproduced across every test run. Its exact size is not a stable number — it's sensitive to how the classification task is phrased, and reporting one run's percentage as settled would overstate what's actually been shown.**

## Finding 3: two corrections and one retracted retraction

- **Poem 3's "vehicle"/"Curricle" pair had the direction backwards in round 2** (built from a published reading edition, not the manuscript). The manuscript's own base word is "Curricle"; "Vehicle" is the offered alternate.
- **Poem 6's "should"→"could" pair, also from round 2, was a different word entirely.** The manuscript marks "Would"→"Could -", not "should".
- **Poem 11's "Root"→"Core" pair was retracted in round 3** as an unconfirmed guess, because the project's own local scrape showed no markup there. Harvard's live record confirms the pair is real — the retraction was premature, caused by the same scrape gap as everything else below.

## Finding 4: real gaps in this project's own 2022 scrape — not, on reflection, a flaw in EDA's scholarship

An earlier draft of this document called the missing markup in poems 1, 5, and 11 an "archive completeness gap," implying the Emily Dickinson Archive's own transcription work was incomplete. That was corrected after direct feedback: the TEI Consortium's own description of the EDA project states that capturing Dickinson's emendations via the critical-apparatus module was an explicit encoding goal, and Harvard's live manifests confirm exactly this — poem 1's "souls→World/selves/Sun" and poem 5's "time→Day" are both fully documented there, and poem 11's "Root→Core" is too. **All three were missing only from this project's own 2022 scrape**, built with custom Python "since there was no API for the original EDA" (this repo's own README) — exactly the kind of process that can miss content inconsistently. Poem 2 gives the clean number either way: of the team's 13 hand-documented pairs, 11 (85%) matched even the incomplete local scrape; all 13 are confirmed in Harvard's full record.

## What this settles, and what it still doesn't

The founding question gets a real, now fully-tested yes: a taxonomy defined in prose can be applied to the complete manuscript record of a real fascicle, blind, with legible reasoning for every one of 84 real readings. What it doesn't settle — and the project was never going to settle by running a classifier — is *which* reading is correct where the classification disagrees with itself run to run, or where two independent readings of the same pair (like "gone"→"known," which every single test called antithesis, including the team's own 2022 instinct that called it "a gulf") point in genuinely different directions than a plainer pair like "Bear"→"hold" (repetitive, undisputed across every run). That's the actual textual-studies question — do we choose one variant over the other, and on what grounds — and a taxonomy this useful, applied this thoroughly, sharpens that question instead of answering it for good.
