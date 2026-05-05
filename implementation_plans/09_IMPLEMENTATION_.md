# Fix Header Overlap and Alignment (Macros Calc)

This plan fixes the issue where the "Protein" and "Calories" headers are overlapping adjacent columns to the left, ensuring they are properly contained and aligned with their numeric data.

## User Review Required

> [!IMPORTANT]
> I will adjust the grid column ratios to provide more breathing room for the header text and ensure that right-aligned text does not overflow its container.

## Proposed Changes

### Styling Updates

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Adjust `grid-template-columns` to give more relative width to the Protein and Calories columns (changing from `1fr` to `1.2fr` or similar) and reducing the Ingredient column width.
- Reduce the horizontal `gap` between columns to `15px` to save space while maintaining separation.
- Ensure `white-space: nowrap` is applied to headers to prevent wrapping, and monitor for overflow.
- Add `text-align: right` to both the content and header cells for Protein and Calories to ensure they stick to the right edge without drifting left.
- Refine the `border-left` on the Protein header to ensure it doesn't push text horizontally in a way that causes overlap.

## Verification Plan

### Manual Verification
- [ ] Open the app and navigate to the **Intro** tab.
- [ ] Inspect the **PROTEIN** and **CALORIES** headers at various screen sizes.
- [ ] Confirm there is no overlap with the columns to their left (Grams and Protein respectively).
- [ ] Verify the text is perfectly aligned with the numbers below.

## Checklist
- [x] Adjust `grid-template-columns` and `gap` in `style.css`
- [x] Verify fix for overlap and alignment in browser
