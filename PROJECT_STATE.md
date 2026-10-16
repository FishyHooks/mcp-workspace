# PROJECT_STATE

**Last updated:** 2026-10-17
**Goal:** Simple calculator app (single-file web app, no dependencies), now a **letter calculator**.

## Current status
Part 1 complete. Plan changed (see below); the old "Part 2" operations were pulled forward and built together with the letter-value change.

## Plan change
Numbers are replaced by letters. Each letter's value is its position in the alphabet (a=1, b=2, c=3 ... z=26), read as base 26.

## What exists
- `index.html`: letter calculator.
  - Keys: a-z (26 letter keys), `+`, `−`, `×`, `÷`, `=`, `C`.
  - Values are bijective base-26 (spreadsheet-column style): `z`=26, `aa`=27, `ab`=28, `az`=52, `ba`=53.
  - Operations: add, subtract, multiply, divide, including chaining (e.g. `b + c × d` resolves left to right as each operator is pressed).
  - Uses `BigInt`, so large values do not lose precision.
- `PLAN_LOG.md`: original 4-part plan (not updated for this plan change).
- `CHECKPOINTS.md`: checkpoint history.
- `DECISIONS.md`: empty.

## Behaviour decisions made for the letter system
- Bijective base-26 has no zero digit, so there is no letter for 0. Zero is shown as `0`.
- Negative results are shown with a `-` prefix (e.g. `a - c` gives `-b`).
- Division is integer division, truncated toward zero (e.g. `d ÷ b` = `a`), because there is no way to show fractions in letters.
- Divide by zero shows `Error`; the next letter starts fresh, and an operator pressed on `Error` treats it as 0.
- "Base26" was interpreted as bijective (a=1 ... z=26) rather than a=0 ... z=25, since the request gave a=1.

## Not built yet
- Keyboard input (type letters, `+ - * /`, Enter, Escape)
- Backspace
- Responsive/accessibility polish and manual test pass
- The old decimal-point item is dropped, since values are whole letters.

## Known caveats
- Not yet tested in a browser; logic was reviewed by reading only.
- The earlier "add-task feature" interpretation (addition operation) is still unconfirmed.
- `PLAN_LOG.md` and `DECISIONS.md` have not been updated for this plan change.

## Next step
Run a manual browser test of the letter math, then add backspace and keyboard input.
