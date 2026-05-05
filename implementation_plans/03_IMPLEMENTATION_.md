# Add Macro Calculator to Intro Tab

This update adds a simple, modern macro calculator to the Intro tab. It allows users to input the amount of 0% Fage Greek Yogurt, Hemp Hearts, and Honey in grams and see the total protein and calorie counts.

## User Review Required

> [!NOTE]
> The calculator will update automatically as values are typed. The design will be kept simple and clean as requested, prioritizing ease of use for regular tracking.

## Proposed Changes

### Logic & Content

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)
- Implement `renderMacroCalc()` to generate the calculator UI.
- Add event listeners for live calculation.
- Define constant macro values for the three ingredients:
    - **0% Fage Greek Yogurt**: 0.103g protein / 0.54 kcal per gram
    - **Hemp Hearts**: 0.311g protein / 5.53 kcal per gram
    - **Honey**: 0g protein / 3.04 kcal per gram
- Update `renderIntro()` to call `renderMacroCalc()`.

### Styling

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Add styles for `.macro-calc-container`.
- Style input fields with a modern, clean look (subtle borders, nice focus states).
- Add styling for the results section to make it clear but not distracting.
- Ensure responsive behavior for mobile use.

## Verification Plan

### Automated Tests
- N/A (Manual visual and functional verification)

### Manual Verification
- Open the "Intro" tab.
- Enter values for each ingredient.
- Verify that the totals for protein and calories update correctly.
- Check the layout on different screen sizes to ensure it remains "easy on the eyes".

## Progress Checklist
- [x] Create Macro Calculator logic in `script.js`
- [x] Add Macro Calculator styles in `style.css`
- [x] Integrate Calculator into `renderIntro`
- [ ] Verify calculation accuracy
- [ ] Final polish of the UI
k