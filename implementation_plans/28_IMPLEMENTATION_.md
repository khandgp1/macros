# 28 — Mobile-Friendly BREAKFAST Tab

## Objective
Make the BREAKFAST tab's macro calculator table, text, and all surrounding elements
scale gracefully to iPhone screen widths (≈390–430 px) while preserving the existing
desktop design exactly.

---

## Context & Current State

| Area | Current behaviour | Problem on mobile |
|---|---|---|
| `#workout-content` | `max-width: 900px`, `padding: 0 20px` | Too wide; no inner scroll guard |
| `macro-calc-container` | `max-width: 600px`, `padding: 30px` | Horizontal overflow on small screens |
| `.table-row` | 4-column grid `1fr 0.25fr 0.6fr 0.6fr` | Columns too tight; text truncates |
| `.col-grams input` | fixed `width: 90px` | Overflows on narrow screens |
| `.col-name` | `font-size: 1rem` | Too large at narrow widths |
| `.col-p` / `.col-c` | `font-size: 1.05rem` | Pushes layout beyond screen edge |
| `.total-row .col-p/c` | `font-size: 1.25rem` | Overflows or causes horizontal scroll |
| `.layout-bento .grid-wrapper` | 2-column grid | Does not collapse on mobile |
| `header` | `padding: 60px 20px` | Wastes vertical space on phones |
| `h1` | `font-size: 2.5rem` | Too large on small screens |
| `.calc-header h3` | `font-size: 1.2rem`, heavy `letter-spacing` | Wraps awkwardly |
| Existing `@media (max-width: 600px)` block | Partial fix, only targets table row + input | Incomplete; misses most elements |

---

## Approach

CSS-only changes inside a dedicated `@media (max-width: 430px)` block
(iPhone-width breakpoint). No JS or HTML structural changes needed.

---

## Checklist

### Phase 1 — Page-Level Layout

- [x] **1.1** Reduce `header` padding (`60px → 30px`) at ≤430px
- [x] **1.2** Scale down `h1` font size (`2.5rem → 1.6rem`) and letter-spacing
- [x] **1.3** Reduce `.subtitle` letter-spacing and font-size slightly
- [x] **1.4** Tighten `#workout-content` padding (`0 20px → 0 12px`) and ensure `box-sizing: border-box`

### Phase 2 — Macro Calculator Container

- [x] **2.1** Reduce `.macro-calc-container` padding (`30px → 14px`) and `border-radius` (`12px → 8px`)
- [x] **2.2** Reduce `.calc-header h3` font-size (`1.2rem → 0.85rem`) and letter-spacing
- [x] **2.3** Remove/tighten `margin-bottom` on `.macro-calc-container` (`50px → 24px`)

### Phase 3 — Table Columns & Typography

- [x] **3.1** Rebalance `.table-row` grid columns for mobile: `2fr 0.9fr 0.75fr 0.75fr`
- [x] **3.2** Reduce `.table-row` padding (`15px 20px → 10px 8px`)
- [x] **3.3** Reduce `.table-row.header` font-size (`0.8rem → 0.65rem`) and letter-spacing
- [x] **3.4** Reduce `.col-name` font-size (`1rem → 0.8rem`)
- [x] **3.5** Reduce `.col-p` / `.col-c` font-size (`1.05rem → 0.85rem`)
- [x] **3.6** Reduce `.total-row .col-p/c` font-size (`1.25rem → 1rem`)
- [x] **3.7** Remove or reduce the fixed `margin-left: 25px` on `.col-p` at mobile

### Phase 4 — Grams Input

- [x] **4.1** Shrink input width (`90px → 56px`) and padding (`8px 12px → 5px 4px`) at ≤430px
- [x] **4.2** Reduce input font-size (`1rem → 0.8rem`)

### Phase 5 — Bento Cards Grid (below the table)

- [x] **5.1** Collapse `.layout-bento .grid-wrapper` from 2-column to 1-column at ≤430px
- [x] **5.2** Reduce `.layout-bento .bento-card` padding at mobile (`20px → 14px`)
- [x] **5.3** Reduce `.layout-bento h3` font-size and letter-spacing slightly

### Phase 6 — Section Description & Focus Heading

- [x] **6.1** Reduce inline `h2` (focus heading) font-size at mobile
- [x] **6.2** Tighten `.section-description` margin and font-size slightly

### Phase 7 — Cleanup & Validation

- [x] **7.1** Remove or merge overlapping rules from the existing `@media (max-width: 600px)` block to avoid conflicts
- [x] **7.2** Test in browser devtools at 390×844 (iPhone 14) and 375×667 (iPhone SE)
- [x] **7.3** Confirm no horizontal scrollbar at any tested width
- [x] **7.4** Confirm desktop layout (>430px) is completely unchanged

---

## Files to Change

| File | Change |
|---|---|
| `style.css` | Add / update `@media (max-width: 430px)` block; merge/remove conflicting `@media (max-width: 600px)` rules for the macro table |

> No changes to `script.js`, `index.html`, or any JSON files.
