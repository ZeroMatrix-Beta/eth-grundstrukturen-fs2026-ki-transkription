# Implementation Plan: Remaining Math-Review Findings (Tier 2/3)

Status: NOT YET APPLIED. These are the ~30 lower-severity findings from the full
14-week review (2026-07-28) that were deliberately left out of the direct-edit pass.
The 6 tier-1 errors were already handled directly (5 got an `ai-note`, 1 duplicate
paragraph in week8 was deleted). Full per-week detail with exact proposed LaTeX is
still available in the review session's scratchpad (`eth-review/week1.md` …
`week14.md`) if needed when implementing these.

Each item below: file, location, one-line issue, proposed environment. Apply as
additive `ai-note`/`explanation-of-steps`/`didactic-insight` blocks, never nested
inside `math-stroke`/other environments (place directly below), and never touching
`spoken-clean` prose except via the permitted parenthetical anchors.

## week1-02-17-25-tuesday.tex
1. `frei(φ)` (~line 622-630) asserted via informal "Bereich" language, no recursive
   F0-F4-style definition given anywhere → add `[PERSISTENT]` `ai-note` with the
   recursive clauses.
2. `var(τ)` (line 612) uses placeholder `x` where every other definition uses `ν`
   → optional one-line notation `ai-note`.

## week3-03-03-25-tuesday.tex
3. Line ~373-374 (spoken-clean): lecturer says "ein n-Tupel ist eine Teilmenge von
   A^n" — false (a tuple is an *element* of A^n, not a subset). The board definition
   right after is correct. Add `[PERSISTENT]` `ai-note` clarifying, without touching
   spoken-clean.

## week5-03-17-25-tuesday.tex
4. Well-definedness of $\omega$ independent of choice of $I_0$ (line ~630-637) never
   justified → `explanation-of-steps` inside the definition's math-stroke.
5. $A^n$ used (line ~839) but never formally defined in a math-stroke, only informal
   spoken prose → add a short `definition` (or `ai-note`) for the n-fold Cartesian
   product.
6. Kuratowski pair "iff" property (line ~254) stated with no proof beyond the
   degenerate case → extend existing `explanation-of-steps` with the case-split
   sketch.

## week6-03-24-25-tuesday.tex
7. "Fall 2" case list for multiplication (line ~739-745) doesn't visibly include the
   positive×positive sub-case (covered by Fall 1, but not obvious) → one clarifying
   sentence added to the existing `explanation-of-steps`.

## week7-03-31-25-tuesday.tex
8. Surjectivity step of the AC⟹WOP construction (line ~789-804) is the crux of the
   proof but asserted with zero justification (unlike injectivity) → add
   `explanation-of-steps` with the standard "extend by one more step" contradiction
   argument.
9. "Minimal element" clause in the Ordinalzahl definition (line ~510) never names the
   relation (implicitly ∈) → small `[PERSISTENT]` `ai-note`.

## week8-04-14-25-tuesday.tex
10. Unjustified step "$v_\delta \notin A_{\delta+1}$" in the Basisexistenzsatz proof
    (line ~478-485) → `explanation-of-steps` with the one-line contradiction argument.
11. Finite-character claim for $\mathcal S$ in TP⟹AC (line ~834-837) asserted with
    proof-level authority but not shown → `explanation-of-steps` spelling out both
    directions.
12. `didactic-insight` (line ~75-77) used for a notation gloss, not an "aha" moment
    → reclassify as `ai-note` with `% [PERSISTENT]`.
13. TikZ diagram (line ~533-557): geometric-visualization loops start at $n=1$,
    causing two distinct ordinals to plot at the same coordinate → start loops at
    $n=2$/$n=3$ instead.

## week9-04-21-25-tuesday.tex
14. "Every infinite cardinal is a limit ordinal" (line ~830, spoken-clean) asserted
    without justification anywhere → `[PERSISTENT]` `ai-note` with the one-line
    successor-cardinal argument.
15. CBS-proof TikZ diagram (line ~505-564) introduces an undefined dual chain
    ($g(B\setminus f(A))$ etc.) never used in the proof text → `ai-note` explaining
    it's a visual refinement, not required by the proof.
16. Kardinalzahl definition uses `<` where spoken intuition uses `≠` (line ~798-804),
    equivalence relies on an unstated fact → `explanation-of-steps`.

## week11-05-05-25-tuesday.tex
17. Satz von Euler applied to a graph with loops (line ~406-434) without addressing
    the earlier caveat that it was only proved for loop-free graphs → `[PERSISTENT]`
    `ai-note` justifying the extension.

## week12-05-12-25-tuesday.tex
18. Euclidean algorithm's stated hypothesis (line ~321-323) allows $a=0$, breaking
    the first division step → `[PERSISTENT]` `ai-note`.
19. Congruence-mod-$n$ definition (line ~812-816) doesn't exclude $n=0$, but the next
    proposition silently requires $n\neq 0$ → short `ai-note`.

## week13-05-19-25-tuesday.tex
20. RSA correctness proof's Fall-2 WLOG (line ~952-963) silently excludes $m=0$ →
    one-sentence tightening of the existing proof text (not a full new block).
21. CRT ring-isomorphism proof (line ~802-813) only verifies multiplicativity, not
    additivity, despite promising both → add the missing symmetric derivation.
22. Lagrange-for-abelian-groups "permutation trick" (line ~486-525), praised verbally
    by the lecturer as "extrem elegant", never captured in a box → add a
    `didactic-insight`.

## week14-05-26-25-tuesday.tex
23. Degree-inequality step in the uniqueness proof (line ~511-514) asserted without
    the $h\neq 0$ / degree-additivity chain spelled out → `explanation-of-steps`.

## week4-03-10-25-tuesday.tex (remaining, non-tier-1)
24. Independence definition (line ~489-494): "Es folgt, dass..." step relies on the
    Korrektheitssatz but doesn't say so → `explanation-of-steps`.
25. Ex Falso Quodlibet remark (line ~325-329) uses `χ` where the proof above uses
    `σ` for the same schema → align variable names.
26. ZF axiom count (7+2=9, line ~608-613) diverges from the common "ZF=8" textbook
    convention → `ai-note` on counting conventions.
27. `T ⊨ σ` notation in the closing summary (line ~790) never formally introduced
    elsewhere → spell out using the established `M ⊨ σ` notation instead.

## week2-02-24-25-tuesday.tex (remaining, non-tier-1)
28. Unused hypothesis `¬(x=0)` in the field-inverse-uniqueness theorem (line
    ~936-1017) never actually discharged in the derivation → `ai-note`.
29. Overstated claim that transitivity of `=` "was proven" (line ~907) when only
    reflexivity/symmetry were shown on the board → `ai-note` cross-referencing the
    deferred exercise.

## week10-step4-04-28-25-tuesday-all-offset-final.tex (remaining, non-tier-1)
30. Malformed set-builder notation `\{x,y\}\in V` in "kanteninduzierter Teilgraph"
    (line ~839-844) — type mismatch, should be `\bigcup_{\{x,y\}\in F}\{x,y\}`.
31. Likely typo "Gesamtschild" → "Gesamtgrad" (line ~658).

---

## Next steps when picking this up

Apply file-by-file, recompile the PDF (pdflatex twice) after each batch or at the
end, check the log for new warnings, then commit. No agents needed — these are all
small, well-scoped additive edits.
