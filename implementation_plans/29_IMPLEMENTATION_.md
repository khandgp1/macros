# 29 — Fix TOTAL Row Wrapping on Mobile

## Objective
Ensure the "Cal" suffix on the TOTAL row's Calories cell—and the "g" suffix
on the Protein cell—never wraps to a second line on iPhone screens (≤430px).
The values must always read as a single compact line (e.g. `0g` / `0 Cal`).

---

## Root Cause

In `script.js` the TOTAL row is rendered as:

```html
<div class="col-p"><span id="total-protein">0</span>g</div>
<div class="col-c"><span id="total-calories">0</span> Cal</div>
```

At `≤430px`, `.total-row .col-p` and `.total-row .col-c` currently use
`font-size: 1rem` (set in plan 28). The word " Cal" is a free-standing text
node inside `col-c`, so when the column is narrow the browser wraps it
onto a second line.

Two properties together will fix this:

1. **`white-space: nowrap`** — prevents the number + unit from ever breaking.
2. **Smaller `font-size`** — reduces the rendered width so the text fits
   comfortably within the `0.75fr` column allocation.

---

## Checklist

### Phase 1 — CSS fix (mobile media query only)

- [ ] **1.1** Inside the existing `@media (max-width: 430px)` block, update
  `.total-row .col-p, .total-row .col-c` to:
  - Reduce `font-size` from `1rem` → `0.8rem`
  - Add `white-space: nowrap`

### Phase 2 — Validation

- [ ] **2.1** Open `http://localhost:3000` in a DevTools mobile viewport
  (390px wide, iPhone 14)
- [ ] **2.2** Confirm "Cal" and "g" each stay on a single line in the TOTAL row
- [ ] **2.3** Confirm ingredient rows are unaffected
- [ ] **2.4** Confirm desktop (>430px) TOTAL row is unchanged

---

## Files to Change

| File | Change |
|---|---|
| `style.css` | Update `.total-row .col-p, .total-row .col-c` inside `@media (max-width: 430px)` |

> No changes to `script.js`, `index.html`, or any JSON files.
