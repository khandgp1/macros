# 35_IMPLEMENTATION_ - Native Ounce Support for Chicken in ingredients.json

The goal is to update `ingredients.json` to store chicken data natively in ounces and update `script.js` to handle both gram-based and ounce-based ingredients without hardcoded conversion factors.

## User Review Required

> [!IMPORTANT]
> The hardcoded conversion factor of 28.35 in `script.js` will be removed. The calculation logic will now dynamically use either `baseGrams` or `baseOz` from the ingredient data.

## Proposed Changes

### Data and Logic Updates

---

#### [MODIFY] [ingredients.json](file:///Users/khandpv1/Desktop/.AntiGrav/macros/ingredients.json)
- Rename `baseGrams` to `baseOz` for `chicken`.
- Rename `defaultGrams` to `defaultOz` for `chicken`.
- Ensure values are correct for ounces (e.g., 19g protein per 6 oz).

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Update `renderMacroCalc` to use `data.defaultGrams || data.defaultOz` for the default input value.
- Update `updateTotals` to use `data.baseGrams || data.baseOz` as the divisor.
- Remove the `rawValue * 28.35` conversion logic, as the input unit (Ounces on Meat tab) will now match the data unit (baseOz).

## Verification Plan

### Manual Verification
1. Open the application and go to the **MEAT** tab.
2. Verify the default value is **3** (or whatever is set in `defaultOz`).
3. Change the value to **6** and verify the protein is **19** and calories are **140**.
4. Switch to the **BREAKFAST** tab and verify calculations are still correct (they will use `baseGrams`).

## Checklist
- [x] Refactor `ingredients.json` for chicken (rename fields)
- [x] Update `script.js` calculation logic to handle `baseOz` / `defaultOz`
- [x] Remove hardcoded conversion factor from `script.js`
- [x] Verify both tabs work correctly
