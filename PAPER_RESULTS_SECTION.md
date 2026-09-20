# Draft "Results" section for "World, Selves, and Sun"

*Written to slot directly after the existing "ExtractV" section and before "Future Directions" in the 2022-23 paper draft. This is a draft for the three of you to revise together, not a final section — check every claim and every number against your own reading before this goes anywhere near a submission.*

---

## Results

The ExtractV pipeline described above was designed in 2022, before the computational skillset existed on this team to build it as specified. This section reports what followed when the underlying question was finally tested: can our taxonomy be applied computationally to the complete critical apparatus of a Dickinson fascicle, and what happens to the taxonomy itself when it is.

### Method

Classification was performed by a large language model, given only the taxonomy's prose definitions above and each base-text/variant pair drawn from R.W. Franklin's apparatus for Fascicle 34, with no access to any prior labeling of the data. This departs from the Gothenburg-model collation and rule-based part-of-speech pipeline originally specified for ExtractV; it is a different computational method, made possible by tools that did not exist in comparable form in 2022, and should be characterized as such rather than as the pipeline first proposed. All 84 documented variant readings across the fascicle's seventeen poems were classified, including three poems (F763, F765, and F770) independently confirmed, from the Archive's own manuscript record, to contain no variants at all, consistent with our 2022 field notes.

### Taxonomic distribution

Table 2 gives the Level 1 distribution across all 84 readings.

| Category | n | % |
|---|---|---|
| Repetitives | 25 | 30% |
| Amplifiers | 21 | 25% |
| Antithesis | 18 | 21% |
| Substitutive (undefined) | 12 | 14% |
| Uncategorized | 6 | 7% |
| Additions | 2 | 2% |

The category labeled "Substitutive" in Table 2 is not one of the five types defined earlier in this paper. It denotes plain, roughly equal-status word-for-word substitution — Dickinson offering "Would" beside "Could," "Root" beside "Core" — that the classifier could not place under repetitives, amplifiers, antithesis, additions, or uncategorized without distortion. Its presence across four independent classification passes, at rates ranging from 14% to 56% depending on how the classification task itself was specified to the model, suggests two things. First, that the gap is a property of the taxonomy rather than an artifact of any single test: some proportion of Dickinson's variant practice in this fascicle does not fit the categories this paper proposed. Second, that the exact proportion should not be reported as a fixed quantity; it is sensitive enough to task specification that we report the observed range rather than a single figure, and treat the instability itself as a finding rather than noise to be averaged away.

### Resolution

A second classification, orthogonal to Table 2, asked whether the poem itself supplies enough information to prefer the base text over the variant or the reverse (Level 2, above). Of the 84 readings, 78 (93%) were classified as non-exclusive — the poem gives no textual basis for choosing between the two wordings — while 4 (5%) were classified as exclusive, and 2 (2%) were additions rather than true alternatives, for which the question of choosing does not apply. This finding bears directly on Cameron's argument that Dickinson's variants "extend the text's identity in ways that make it seem potentially limitless" (6): tested here as a measurable property of one fascicle's complete apparatus rather than a qualitative reading of selected examples, the proportion of genuinely unresolved variants is high enough to support Cameron's claim in something close to its strongest form, at least for the fascicle examined.

### Data quality

The 2022 extraction on which this project's earlier concordance work relied was cross-referenced against the manuscript-verified data used above and found to have approximately 87% recall, with most of the remaining variants absent rather than misrepresented — a consequence of variant types (phrase-length alternates spanning two lines, additions with no marked base word, readings that exist only in a second manuscript witness) that a word-level extraction process was not designed to capture. One misrecorded reading was identified in that dataset ("Sun"/"sustain," where the manuscript reads "Sun"/"Noon") and should be corrected in any future use of it.

### Summary

Taken together, these results answer the question this project posed in 2022 more fully than the project expected to when it began. The taxonomy can be applied computationally to complete manuscript data, with legible, individually defensible classifications for each reading. Doing so, however, revealed a category of variant relationship — plain substitution — that the taxonomy as originally formulated does not name, and confirmed, at a scale beyond what close reading of a handful of examples could establish, that the great majority of Dickinson's variants in this fascicle remain genuinely, not just apparently, unresolved.
