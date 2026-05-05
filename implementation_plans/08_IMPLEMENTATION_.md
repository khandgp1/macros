# Column Header Alignment (Macros Calc)

This plan ensures that the column headers in the Macros Calculator are visually aligned with the data in each column.

## User Review Required

> [!NOTE]
> I will align the "Grams", "Protein", and "Calories" headers to match their respective content (Right-aligned for numeric data, centered for input fields).

## Proposed Changes

### Styling Updates

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Update `.col-p` and `.col-c` headers to ensure they are explicitly right-aligned to match the numeric content.
- Update `.col-grams` (both header and content) to be centered for better visual balance.
- Adjust the `padding-left` on the Protein header divider to ensure it doesn't shift the label off-center from its data.
- Ensure the input fields in `.col-grams` are centered within their column.

## Verification Plan

### Manual Verification
- [ ] Open the app and navigate to the **Intro** tab.
- [ ] Verify that the **Grams** header is centered over the input boxes.
- [ ] Verify that the **Protein** header is right-aligned over the protein values.
- [ ] Verify that the **Calories** header is right-aligned over the calorie values.
- [ ] Check for visual consistency across different browser window widths.

## Checklist
- [x] Update `.col-grams` alignment in `style.css`
- [x] Update `.col-p` and `.col-c` header alignment in `style.css`
- [x] Verify alignment in browser
