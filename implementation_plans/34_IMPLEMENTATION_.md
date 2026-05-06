# 34_IMPLEMENTATION_ - Change Units to Ounces for Meats Macro Table

The goal is to update the `MEATS MACRO TABLE` on the `MEAT` tab to use `OUNCES` as the unit of measurement instead of `GRAMS`. The `BREAKFAST MACRO TABLE` will remain in `GRAMS`.

## User Review Required

> [!IMPORTANT]
> This change only affects the `MEAT` tab. The calculation logic will be updated to handle the conversion from ounces to grams (1 oz = 28.35g) since the underlying ingredient data is stored in grams.

## Proposed Changes

### UI Updates

---

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Update the table header in `renderMacroCalc` to show "Ounces" when `isMeatTab` is true.
- Update the calculation logic in `updateTotals` to multiply the input value by 28.35 if `isMeatTab` is true, ensuring the protein and calorie calculations remain accurate against the gram-based `ingredients.json`.
- Update the default value for `chicken` to be in ounces (e.g., 7 oz instead of 200g).

#### [MODIFY] [ingredients.json](file:///Users/khandpv1/Desktop/.AntiGrav/macros/ingredients.json)
- Update `defaultGrams` for `chicken` to `7` (representing 7 ounces) to align with the new unit.

## Verification Plan

### Manual Verification
1. Open the application and go to the **MEAT** tab.
2. Verify the column header now says **Ounces**.
3. Verify the default value for chicken is **7**.
4. Change the value to **1** and verify the protein and calories update correctly (1 oz = ~7.6g protein, ~54 cal).
5. Switch to the **BREAKFAST** tab and verify it still says **Grams** and uses the old logic.

## Checklist
- [x] Update `ingredients.json` default value for chicken
- [x] Modify `renderMacroCalc` in `script.js` to display "Ounces" header for Meat tab
- [x] Update `updateTotals` logic in `script.js` to handle ounce-to-gram conversion for Meat tab
- [x] Verify calculations on both tabs
