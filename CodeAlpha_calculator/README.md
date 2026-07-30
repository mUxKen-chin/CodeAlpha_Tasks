# Calculator — Atelier MK-01

A single-file, self-contained calculator built with HTML, CSS, and vanilla JavaScript. No frameworks, no build step, no dependencies beyond two Google Fonts.

## Files

- `calculator.html` — everything (markup, styles, logic) in one file. Just open it in a browser.

## Features

- **Core arithmetic:** addition, subtraction, multiplication, division
- **Live chained calculation:** e.g. typing `5 + 3 ×` immediately shows the running result before you finish the expression
- **Left-to-right evaluation:** matches the behavior of the iOS/iPhone calculator rather than strict math order-of-operations (so `5 + 3 × 2 =` gives `16`, not `11`)
- **Percent (`%`):** relative to the previous operand when mid-calculation, or a straight `/100` otherwise
- **Backspace:** removes one digit at a time
- **All clear (`AC`):** resets the calculator fully
- **Repeat-equals:** pressing `=` again after a result repeats the last operation (e.g. `2 × =` gives `4`, then `8`, then `16`...)
- **Divide-by-zero handling:** shows a styled `Error` state instead of `Infinity`/`NaN`
- **Number formatting:** thousand separators and scientific notation for very large numbers
- **Keyboard support:**

  | Key | Action |
  |---|---|
  | `0`–`9` | Digits |
  | `.` | Decimal point |
  | `+` `-` `*` `/` | Operators |
  | `Enter` or `=` | Equals |
  | `Backspace` | Delete last digit |
  | `Escape` | Clear all |
  | `%` | Percent |

## Design notes

- **Palette:** warm near-black background with a single brass/gold accent — one accent color used deliberately rather than a generic dark-mode default.
- **Typography:** JetBrains Mono for the numeric display (tabular figures, precision-instrument feel), Space Grotesk for button labels.
- **Physical metaphor:** the display sits in a recessed "screen" with an inset shadow, and buttons compress on press (`translateY` + collapsing shadow) to feel tactile rather than flat — modeled after classic instrument-style calculators (Braun/Rams territory) rather than a flat app UI.

## Known logic

The calculator maintains three pieces of state: `current` (the number being typed), `previous` (the stored operand), and `operator` (the pending operation). Pressing an operator resolves any pending calculation immediately (left-to-right), then stores the new operator — this is what produces the iPhone-style chained behavior instead of standard math precedence.

## Browser support

Works in any modern browser. No polyfills needed; uses standard ES6+ JavaScript (arrow functions, template literals, `dataset`).
