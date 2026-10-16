# CHECKPOINTS

## CP1: Part 1 complete (2026-10-17)
- Wrote 4-part plan in PLAN_LOG.md.
- Built `index.html` with calculator UI and working addition (digits, `+`, `=`, `C`, chaining).
- Updated PROJECT_STATE.md.
- Verified: code reviewed by reading only; not run in a browser.
- Open question: "add-task feature" interpreted as the addition operation.
- Next: Part 2 (subtract, multiply, divide).

## CP2: Plan change to letter calculator + all four operations (2026-10-17)
- Plan changed: digits replaced by letters a-z (a=1 ... z=26), read as bijective base-26.
- Rebuilt `index.html`: 26 letter keys, `+`, `−`, `×`, `÷`, `=`, `C`; BigInt math; letter/number conversion helpers.
- Decisions: zero shown as `0`; negatives use `-` prefix; division is integer (truncated toward zero); divide by zero shows `Error`.
- Updated PROJECT_STATE.md. PLAN_LOG.md and DECISIONS.md left untouched.
- Verified: code reviewed by reading only; not run in a browser.
- Next: manual browser test, then backspace and keyboard input.
