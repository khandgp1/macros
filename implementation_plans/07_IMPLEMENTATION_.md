# Remove Grams Column Spinners (Macros Calc)

This plan removes the native browser increment/decrement buttons (spinners) from the Grams input fields in the Macros Calculator to provide a cleaner look.

## User Review Required

> [!NOTE]
> Users will still be able to enter numbers manually or use keyboard arrows if the browser supports it, but the visual "up/down" arrows inside the input field will be removed.

## Proposed Changes

### Styling Updates

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Add CSS rules to hide `-webkit-outer-spin-button` and `-webkit-inner-spin-button` for the grams input fields.
- Set `-moz-appearance: textfield` for Firefox compatibility.
- Ensure the targeting is scoped to `.col-grams input` to avoid affecting other potential number inputs in the app.

## Verification Plan

### Manual Verification
- [ ] Open the app and navigate to the **Intro** tab.
- [ ] Hover over and click into the **Grams** input fields.
- [ ] Verify that the up/down arrow buttons (spinners) are no longer visible.
- [ ] Ensure that typing numbers still works correctly and updates the macros.

## Checklist
- [x] Add CSS to `style.css` to hide number input spinners
- [x] Verify change in browser
