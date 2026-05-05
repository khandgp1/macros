# Center Align Macro Headers (Macros Calc)

This plan updates the Macros Calculator to center-align the "Protein" and "Calories" headers, matching the alignment of the "Grams" header.

## Proposed Changes

### Styling Updates

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Remove the `text-align: right` override for `.table-row.header .col-p` and `.table-row.header .col-c`.
- Ensure that the shared rule setting these headers to `text-align: center` is preserved.
- Keep the numeric content (the data rows) right-aligned for readability, unless further changes are requested.

## Verification Plan

### Manual Verification
- [ ] Open the app and navigate to the **Intro** tab.
- [ ] Verify that **GRAMS**, **PROTEIN**, and **CALORIES** headers are all centered within their respective columns.
- [ ] Confirm that the numeric data below remains properly aligned (right-aligned for results, centered for inputs).

## Checklist
- [x] Update header alignment in `style.css`
- [x] Verify centered headers in browser
