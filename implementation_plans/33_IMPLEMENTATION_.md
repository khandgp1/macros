# 33_IMPLEMENTATION_ - Separate Macro Tables for Breakfast and Meat Tabs

The goal is to stop the `MEAT` tab from mirroring the `BREAKFAST` tab's macro table. We will update the table title and the list of ingredients shown in each tab.

## User Review Required

> [!IMPORTANT]
> The `MEAT` tab will now only show "Kirkland Rotisserie Chicken". The `BREAKFAST` tab will continue to show the existing breakfast ingredients.

## Proposed Changes

### [Component Name] Macro Data and Logic

---

#### [MODIFY] [ingredients.json](file:///Users/khandpv1/Desktop/.AntiGrav/macros/ingredients.json)
- Add `chicken` entry for "Kirkland Rotisserie Chicken" with placeholder macro values.

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Update `renderMacroCalc` to accept a `tabType` parameter.
- Dynamically set the title to "BREAKFAST MACRO TABLE" or "MEATS MACRO TABLE".
- Filter ingredients: 
    - `breakfast` tab shows `fage`, `hemp`, `honey`.
    - `meat` tab shows `chicken`.
- Update `renderIntro` to pass the current tab title to `renderMacroCalc`.
- Ensure unique IDs for inputs/spans if they coexist, though currently they are replaced in the DOM.

## Verification Plan

### Manual Verification
1. Open the application.
2. Click on the **BREAKFAST** tab.
    - Verify the title is "BREAKFAST MACRO TABLE".
    - Verify it shows Fage, Hemp, and Honey.
3. Click on the **MEAT** tab.
    - Verify the title is "MEATS MACRO TABLE".
    - Verify it shows "Kirkland Rotisserie Chicken".
    - Verify that entering grams updates the protein and calories correctly.

## Checklist
- [x] Add chicken to `ingredients.json`
- [x] Refactor `renderMacroCalc` in `script.js` to accept `tabType`
- [x] Implement conditional title in `renderMacroCalc`
- [x] Implement ingredient filtering in `renderMacroCalc`
- [x] Update `renderIntro` calls to pass the tab title
- [x] Test tab switching and calculations
