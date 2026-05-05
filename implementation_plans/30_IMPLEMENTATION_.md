# 30 — Restore Macro Table Labels and Units with Mobile Fit

## Objective
Restore the full labels ("Protein", "Calories") and units ("g", "Cal") in the macro table, while ensuring the entire row still fits on a single line on mobile devices (≤430px) using CSS optimizations.

## Proposed Changes

### [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)

#### [MODIFY]
- Revert headers "P" and "C" back to "Protein" and "Calories".
- Restore the "g" suffix in the ingredient rows for protein.
- Restore the "g" and "Cal" suffixes in the total row.

### [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)

#### [MODIFY]
- In the `@media (max-width: 430px)` block:
    - Reduce the font size of the headers and values significantly (e.g., 0.6rem - 0.7rem).
    - Reduce the horizontal padding of the table cells.
    - Adjust `grid-template-columns` to optimize for the longer labels (e.g., reduce the name column proportion).
    - Use `letter-spacing` reduction to save a few pixels.
    - Ensure `white-space: nowrap` is kept to force single-line display.

## Checklist

### Phase 1 — Script Restoration
- [x] **1.1** Update `renderMacroCalc` in `script.js`:
    - Header: "P" -> "Protein"
    - Header: "C" -> "Calories"
    - Ingredient row protein: `<span id="${key}-p">0</span>` -> `<span id="${key}-p">0</span>g`
    - Total row protein: `<span id="total-protein">0</span>` -> `<span id="total-protein">0</span>g`
    - Total row calories: `<span id="total-calories">0</span>` -> `<span id="total-calories">0</span> Cal`

### Phase 2 — CSS Optimizations for Fit
- [x] **2.1** In `style.css`, within the `@media (max-width: 430px)` block:
    - Reduce `.table-row.header` font-size to `0.6rem`.
    - Reduce `.col-p, .col-c` font-size to `0.7rem`.
    - Reduce `.table-row` padding to `10px 4px`.
    - Adjust `grid-template-columns` (e.g., `1.8fr 0.8fr 0.7fr 0.7fr`).
    - Apply `letter-spacing: -0.2px` if needed.

### Phase 3 — Verification
- [ ] **3.1** Open `http://localhost:3000` on a mobile viewport.
- [ ] **3.2** Confirm "Protein" and "Calories" fit in the header without wrapping.
- [ ] **3.3** Confirm "0g" and "0 Cal" fit in the total row on a single line.
- [ ] **3.4** Confirm ingredient rows look balanced.
