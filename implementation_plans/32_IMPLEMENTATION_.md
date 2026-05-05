# Implementation Plan - Numeric Keypad for Breakfast Calculator

Update the macro calculator on the `BREAKFAST` tab to trigger the numeric keypad on mobile devices for better usability.

## Proposed Changes

### [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)

#### [MODIFY] [script.js](file:///Users/khandpv1/Desktop/.AntiGrav/macros/script.js)

- Update the `input` element within the `renderMacroCalc` function to include the `inputmode="decimal"` attribute.
- This will ensure that mobile browsers open the numeric keypad (including a decimal point) instead of the standard text keyboard.

```javascript
// Target line in renderMacroCalc
<input type="number" id="${key}-grams" placeholder="0" min="0" value="${ingredientsData[key].defaultGrams || 0}">
// Becomes
<input type="number" inputmode="decimal" id="${key}-grams" placeholder="0" min="0" value="${ingredientsData[key].defaultGrams || 0}">
```

## Verification Plan

### Manual Verification
- Open the application on a mobile device or use the browser's mobile emulation mode.
- Navigate to the `BREAKFAST` tab.
- Click on a "Grams" input field.
- Confirm that the numeric keypad opens.

## Checklist
- [x] Add `inputmode="decimal"` to ingredients input in `renderMacroCalc` function in `script.js`
- [x] Verify numeric keypad opens on mobile viewports
