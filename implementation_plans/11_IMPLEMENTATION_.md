# Adjust Macro Header Positioning (Macros Calc)

This plan fine-tunes the positioning of the "Protein" and "Calories" headers. Although set to center-aligned, they currently appear too far to the left relative to the right-aligned numeric data. We will push them further to the right to achieve a better visual balance.

## Proposed Changes

### Styling Updates

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Add `padding-left` to `.table-row.header .col-p` and `.table-row.header .col-c` to shift the centered text further to the right.
- Alternatively, switch back to `text-align: right` but with a `padding-right` that matches the average width of the numeric units (like "g") to keep them centered over the numbers.
- I will start by adding a `20px` left padding to the centered headers to push them into a more visually aligned position over the numeric values.

## Verification Plan

### Manual Verification
- [ ] Open the app and navigate to the **Intro** tab.
- [ ] Verify that the **PROTEIN** and **CALORIES** headers look centered relative to the column content.
- [ ] Confirm they have been pushed further to the right as requested.

## Checklist
- [ ] Adjust header positioning with `padding-left` in `style.css`
- [ ] Verify visual alignment in browser
