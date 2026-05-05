# 22_IMPLEMENTATION_ - Prepopulate Macros Table

Prepopulate the macros calculator with default gram values for common ingredients (Yogurt, Hemp Hearts, Honey) upon initial load.

## Proposed Changes

---

### Data Updates

#### [MODIFY] [ingredients.json](file:///Users/khandpv1/Desktop/.AntiGrav/macros/ingredients.json)
- Add a `defaultGrams` property to each ingredient entry.
- Set `defaultGrams` to 170 for Yogurt, 30 for Hemp Hearts, and 30 for Honey.

---

### Logic Updates

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Update the HTML generation in `renderMacroCalc()` to set the `value` attribute of the gram inputs using `ingredientsData[key].defaultGrams`.
- Ensure `updateTotals()` is called immediately after the table is rendered so that the initial Protein and Calories are displayed correctly.

## Verification Plan

### Manual Verification
- **Initial Load Test**: Refresh the page and verify that the "Grams" inputs are prepopulated with 170, 30, and 30 respectively.
- **Calculation Test**: Verify that the "Protein", "Calories", and "TOTAL" rows reflect the prepopulated values immediately upon load.
- **Persistence Test**: Ensure that changing the values manually still works as expected.

## Implementation Checklist
- [x] Update `ingredients.json` with `defaultGrams`.
- [x] Update `renderMacroCalc` in `script.js` to use `defaultGrams`.
- [x] Trigger `updateTotals` on initial render.
- [x] Verify prepopulated values and totals on page load.
