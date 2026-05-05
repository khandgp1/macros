# 21_IMPLEMENTATION_ - Externalize Macro Data

Externalize the macro nutritional data (Protein, Calories) from the hardcoded object in `script.js` into a separate, manually editable JSON file. This allows for easier updates to nutritional information without modifying the application logic.

## User Review Required

> [!IMPORTANT]
> I have designed the new `ingredients.json` file to use a "Base Grams" (serving size) approach. This makes it easier for you to copy numbers directly from nutritional labels (e.g., values per 100g).

## Proposed Changes

---

### Data Storage

#### [NEW] [ingredients.json](file:///Users/khandpv1/Desktop/.AntiGrav/macros/ingredients.json)
- Create a JSON file containing the ingredients and their nutritional facts.
- Each ingredient will include: `name`, `baseGrams`, `protein`, and `calories`.

---

### Logic Updates

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Add a global `ingredientsData` variable to store the fetched data.
- Update the `init()` function to fetch `ingredients.json` alongside `program.json`.
- Modify `renderMacroCalc()` to use `ingredientsData` instead of the hardcoded `macros` object.
- Update the calculation logic (`updateTotals`) to derive per-gram multipliers from the `baseGrams` in the JSON file.

## Verification Plan

### Automated Tests
- Not applicable (manual verification preferred for UI logic).

### Manual Verification
- **Fetch Test**: Open the browser console to ensure `ingredients.json` is fetched successfully.
- **Calculation Test**: Enter grams in the calculator and verify that Protein and Calories update correctly based on the values in `ingredients.json`.
- **Edit Test**: Manually change a value in `ingredients.json`, refresh the page, and confirm the calculator uses the new value.

## Implementation Checklist
- [x] Create `ingredients.json` with current data.
- [x] Modify `script.js` to fetch `ingredients.json` in `init()`.
- [x] Update `renderMacroCalc` to use dynamic data.
- [x] Update `updateTotals` calculation logic.
- [x] Verify functionality in the browser.
