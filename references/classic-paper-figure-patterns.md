# Classic Paper Figure Patterns

This reference records figure patterns inspected from original papers. It is a design and teaching reference, not a license to copy figures or data. Preserve the paper's citation, page/figure number, and reuse conditions when a source figure is shown.

## Papers inspected

| Paper | Figure inspected | Pattern to learn | Teaching use |
|---|---|---|---|
| Vaswani et al., *Attention Is All You Need* (2017) | Fig. 1, Fig. 2 | One overview architecture with repeated blocks; one local operator diagram | Show the whole path first, then zoom into Q/K/V or a sublayer |
| Fedus et al., *Switch Transformers* (2021) | Fig. 1 | Two plots with a shared claim: scaling behavior and training comparison | Keep a comparison paired: structural change plus measured consequence |
| Dao et al., *FlashAttention* (2022) | Fig. 1, Fig. 2 | Memory hierarchy + tiled algorithm path + speed/memory result | Connect hardware resource, operation, and outcome in one visual argument |
| Hu et al., *LoRA* (2021) | Fig. 1 | Reparameterization diagram with frozen base matrix and low-rank branch | Make “what is frozen, what is trained, and how they recombine” visible |
| Ouyang et al., *Training language models to follow instructions with human feedback* (2022) | Fig. 2 | Three numbered stages with repeated prompt/model/data objects | Use a stable process strip and show the same object moving through stages |
| Rafailov et al., *Direct Preference Optimization* (2023) | Fig. 1 | Side-by-side RLHF and DPO pipelines | Compare alternatives on the same input, with different optimization paths |

## Extracted rules

1. **Overview before detail**: start with one dominant object or system path. Use a local detail only after the learner can locate it in the overview.
2. **One figure, one claim**: a panel may contain several marks, but its title and caption should answer one learner question. Do not assemble unrelated mini-cards into a dashboard.
3. **Relationship beats decoration**: arrows, alignment, shared axes, repeated shapes, and visible input/output identities carry the explanation. Color is a secondary cue.
4. **Comparison needs a fixed reference**: keep the same categories, scale, units, and input case when toggling alternatives. Include a baseline or reference series when the claim is relative.
5. **Mechanism and consequence belong together**: when the lesson is an engineering tradeoff, pair the mechanism diagram with the resource/performance view that explains why it matters.
6. **Stages reuse the same nouns**: in a pipeline, keep the prompt, model, answer, reward, or tensor visibly identifiable as it moves. Avoid five stages that only differ by headings.
7. **Captions do real teaching**: state what to inspect, what changed, and what conclusion is supported. A caption is not a duplicate title.
8. **Small number of panels**: prefer two or three purposeful panels with a shared reading direction. Add a fourth only when it closes the causal chain.
9. **Direct labels and units**: label bars, paths, tensor shapes, memory levels, and axes near the marks. Do not force the learner to decode a distant legend for essential meaning.
10. **Evidence boundary**: distinguish source figure marks, reproduced source data, and teaching annotations. Never present an idealized reconstruction as an empirical result.

## Application to interactive companions

- Use the original source figure or a faithful local redraw as the visual anchor when it directly teaches the relationship.
- Put interaction on the marks: toggle a bar series, highlight a route, reveal a tensor block, move along a stage, or compare two paths. A text-only state switch is insufficient.
- Keep the first state equivalent to the nearby static explanation. Add one normal state and one meaningful comparison or boundary state.
- Keep a static fallback in the Markdown note and cite the exact source page/figure next to the visual.
- Record a short visual design note: learner question, focal object, source figure, interactive change, and conclusion that the interaction supports.

## Source URLs

- https://arxiv.org/abs/1706.03762
- https://arxiv.org/abs/2101.03961
- https://arxiv.org/abs/2205.14135
- https://arxiv.org/abs/2106.09685
- https://arxiv.org/abs/2203.02155
- https://arxiv.org/abs/2305.18290

Accessed 2026-10-26. Figure observations were made from the original arXiv PDFs; no paper figure was copied into this reference.
