# PROJECT_STATE

**Last updated:** 2026-10-17
**Goal:** Letter calculator (single-file web app, no dependencies).

## Current status
All planned features are built (CP3). The only open item is a manual browser test, which has not been possible in this workspace.

## How it works
Letters are numbers: a=1 ... z=26, read as bijective base-26 (`z`=26, `aa`=27, `ab`=28, `az`=52, `ba`=53). See DECISIONS.md for all behaviour rules.

## What exists
- `index.html`: the whole app.
  - Keys: a-z (each with a small number label), `+`, `−`, `×`, `÷`, `=`, ⌫ (delete), `C` (clear).
  - Screen shows: expression line (`bc (55) + d (4) =`), main letter display, decimal value of the display (`= 731`), and per-letter breakdown (`a=1 · b=2`).
  - Operations: add, subtract, multiply, divide (integer, truncated toward zero), chaining left to right, `BigInt` math.
  - Delete (backspace) and done (equals with result and expression).
  - Keyboard: a-z, `+ - * /`, Enter or `=`, Backspace/Delete, Escape.
  - UI design: card layout, light/dark theme, active-operator ring, key press flash, responsive, focus states, aria labels, reduced-motion support.
- `PLAN_LOG.md`: rewritten plan with statuses.
- `CHECKPOINTS.md`: CP1 to CP3.
- `DECISIONS.md`: D1 to D8.
- `hello.txt`: leftover test file from the first session; not part of the app.
- `alpha-calculator/`: empty folder, unused.

## Not done
- Manual browser test of the math and the UI. Logic and layout were reviewed by reading only.
- Decimal point: dropped on purpose (whole letters only).

## Known caveats and open questions
- "Add-task feature" was read as the addition operation (unconfirmed).
- "Done and delete features" was read as equals and backspace (unconfirmed). PLAN_LOG.md had no items with those names.
- Backspace does nothing while a result or stored operand is showing.
- Very long letter strings will scroll sideways in the display rather than shrink.

## Next step
Open `index.html` in a browser and test: `b + c =` gives `e`; `z + a =` gives `aa`; `a − c =` gives `-b`; `d ÷ b =` gives `b`; `a − a =` shows `0`; backspace and keyboard input; light and dark themes; a narrow phone width. (Divide by zero can't be typed, since no key makes 0 as an operand; the Error path is only reachable in theory.) Fix anything found, then record CP4.
