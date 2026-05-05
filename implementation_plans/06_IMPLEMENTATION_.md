# Macros Calculator Updates (Intro Tab)

This plan updates the Macros Calculator to improve clarity, consistency, and naming conventions as requested.

## User Review Required

> [!NOTE]
> The protein values will now be rounded to the nearest whole number (e.g., 20.6g becomes 21g) to satisfy the "whole numbers only" requirement.

## Proposed Changes

### Macros Logic and Display

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Update `macros.yogurt.name` to `"0% Fage Greek Yogurt"`.
- Change initial protein displays from `0.0g` to `0g`.
- Update `updateTotals` function to use `Math.round()` for protein calculations (both per-ingredient and total).
- Change the unit label in the total row from `kcal` to `Cal`.

### Styling Improvements

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Increase the column separation between "Protein" and "Calories" headers.
- Add subtle vertical spacing or alignment adjustments to ensure the headers don't feel "bunched up".
- Specifically, I will increase the `column-gap` in `.table-row` and ensure headers have distinct visual breathing room.

## Verification Plan

### Manual Verification
- [ ] Open the app and navigate to the **Intro** tab.
- [ ] Verify the yogurt name is "0% Fage Greek Yogurt".
- [ ] Enter various gram values and ensure Protein and Calories are always displayed as whole numbers.
- [ ] Check that the total unit is `Cal`.
- [ ] Visually inspect the header to ensure "PROTEIN" and "CALORIES" are clearly separated.

## Checklist
- [x] Update `script.js` with new naming and rounding logic
- [x] Update `script.js` HTML template for unit change and initial values
- [x] Update `style.css` for better header separation
- [x] Final verification in browser
