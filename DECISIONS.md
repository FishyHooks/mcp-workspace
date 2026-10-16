# DECISIONS

## D1: Letter values are bijective base-26 (CP2)
a=1 ... z=26, then `aa`=27, `ab`=28 (spreadsheet-column style). There is no zero digit. Chosen over a=0 ... z=25 because the request said a=1.

## D2: Zero, negatives, errors (CP2)
- Zero is shown as `0` (no letter for it).
- Negative results use a `-` prefix (`a - c` gives `-b`).
- Divide by zero shows `Error`. The next letter starts fresh. An operator pressed on `Error` treats it as 0.

## D3: Division is integer division (CP2)
Truncated toward zero (`d / b` = `a`), because fractions cannot be shown as letters. Decimals were dropped from the plan.

## D4: "Add-task feature" read as the addition operation (CP1)
Nothing in the workspace defined a task list. Unconfirmed.

## D5: "Done and delete features" read as equals and backspace (CP3)
PLAN_LOG.md had no items named "done" or "delete". Interpreted as:
- **delete** = backspace: removes the last typed letter. Falls back to `0` when empty. On `Error` it clears everything. It does nothing while a result or stored operand is showing (nothing was typed). Mapped to the on-screen ⌫ key and the Backspace/Delete keys.
- **done** = equals: finishes the calculation, shows the result and the full expression above it.
Unconfirmed. If something else was meant (for example a task list with done/delete), say so.

## D6: Number equivalents on screen (CP3)
- A line under the display shows the decimal value of what is on the display (`= 731`, with thousands separators).
- A line under that shows each letter's value (`a=1 · b=2 · c=3`) for entries up to 8 letters; longer entries show "N letters".
- The expression line above the display shows operands as `letters (number)`, e.g. `bc (55) + d (4) =`.
- Each letter key also shows its number in a small corner label.

## D7: Keyboard mapping (CP3)
Letters a-z (case-insensitive), `+ - * /`, Enter or `=` for equals, Backspace/Delete for delete, Escape for clear. Ctrl/Cmd/Alt combinations are ignored so browser shortcuts still work.

## D8: UI design (CP3)
Rounded card, screen panel with expression / main display / number value / letter breakdown, accent-coloured operator and equals keys, danger-tinted delete and clear keys, active-operator ring, key press flash, light and dark themes via `prefers-color-scheme`, reduced-motion support. Keys sit in a 7-column grid: 26 letters + delete + clear = 28 keys, 4 rows.
