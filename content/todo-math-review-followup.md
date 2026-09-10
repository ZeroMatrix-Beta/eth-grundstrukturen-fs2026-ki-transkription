# Math-Review: Status und offene Punkte

Status: **Die 31 Tier-2/3-Findings der Review vom 2026-07-28 sind abgearbeitet.**
Sie wurden teils im Commit `7d30677` (Tier 1), teils im zweiten Review-Durchgang
(2026-09-11, alle 14 Wochen erneut gelesen) angewendet. Was unten steht, sind nur
noch die Punkte, die bewusst offen bleiben — plus die Sachen, die ohne die
Originalfolien oder das Video nicht entschieden werden können.

## Bewusst offen gelassen

1. **week13, Permutationstrick im Lagrange-Beweis (~Zeile 490).** Der Dozent nennt
   den Beweis mündlich „extrem elegant"; die Pointe steht derzeit nur als
   Klammerbemerkung im `spoken-clean`, nicht als eigener `didactic-insight`.
   Rein stilistisch — der Inhalt ist da.

## Nur mit Folie/Video entscheidbar

2. **week10, `A^4`-Matrix (~Zeile 1090).** Die projizierte Matrix passt nicht zu dem
   weiter oben gezeichneten 6-Knoten-Digraphen (Spalte 3 dürfte ausserhalb der
   Diagonale nur Nullen enthalten, und der hervorgehobene Wert `a_{6,5}=4` müsste
   dort `0` sein). Steht als `ai-note` daneben. Zu klären: fehlen dem TikZ-Bild
   Kanten, oder wurde die Matrix falsch übernommen? (Video ca. 01:19:44–01:25:38.)

3. **week6, Multiplikation Dedekindscher Schnitte, Fall 1 (~Zeile 740).** In der
   Definition muss `p < 0` durch `p ≤ 0` ersetzt werden, sonst fehlt der Menge
   genau das Element `0` und **(D1)** ist verletzt (Begründung steht als `ai-note`
   direkt darunter). Bewusst *nicht* still in der Definition korrigiert, weil nicht
   überprüfbar ist, was auf der Tafel stand. Wenn klar ist, dass es ein
   Transkriptionsfehler war: Formel direkt anpassen und die `ai-note` löschen.

4. **week1, Nummerierung der logischen Axiome (~Zeile 745).** Woche 1 listet
   `L_0`–`L_15`, ab Woche 2 wird dieselbe Liste mit einem zusätzlichen Schema
   `L_9: ¬φ → (φ → ψ)` geführt, wodurch sich alles Nachfolgende um eins
   verschiebt. Eine `[PERSISTENT]`-`ai-note` in Woche 1 erklärt das. Die Liste in
   Woche 1 wurde *nicht* umnummeriert, weil unklar ist, ob die Folie dort
   tatsächlich kürzer war oder ob beim Transkribieren ein Axiom verloren ging.
   Falls Letzteres: `L_9` in Woche 1 ergänzen, `L_9`–`L_15` zu `L_10`–`L_16`
   verschieben, Note löschen.

## Konventionen für künftige Durchgänge

- Additive Blöcke (`ai-note`, `explanation-of-steps`) statt Umschreiben.
- `didactic-insight` ist ein Stand-alone-Container und darf **nie** in
  `math-stroke` stehen (war an drei Stellen der Fall, ist behoben; Prüfbefehl:
  `awk '/begin[{]math-stroke/{d=1} /end[{]math-stroke[}]/{d=0} /begin[{]didactic-insight/{if(d) print FILENAME":"NR}' content/week*.tex`).
- `spoken-clean` bleibt gesprochen; Eingriffe nur über die erlaubten
  Klammer-Anker `(...)`, `[Anmerkung: ...]`, `(Recall: ...)`.
- Nach jedem Kapitel `pdflatex` laufen lassen und das Log auf `^!` prüfen.
