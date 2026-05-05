# 17_IMPLEMENTATION_ - Further Reduce Column Spacing in Macros Calculator

Reduce the visual spacing between the **INGREDIENT** column and the **GRAMS** column by approximately half of the current distance.

## Proposed Changes

### Macros Calculator UI

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)

Reduce the grid gap and further refine column proportions to tighten the layout.

- **Gap Reduction**: Change `gap: 0 10px;` to `gap: 0 5px;` (directly halving the defined gutter).
- **Column Proportion Refinement**: Adjust `grid-template-columns` to ensure the first two columns stay tight.
    - **Current**: `grid-template-columns: 1fr 0.4fr 1fr 1fr;`
    - **Proposed**: `grid-template-columns: 1fr 0.3fr 1fr 1fr;` (Incremental tightening to accompany the gap change).

## Checklist

- [x] Modify `.table-row` in `style.css` to change `gap` from `10px` to `5px`.
- [x] Adjust `grid-template-columns` for `.table-row` to `1fr 0.3fr 1fr 1fr`.
- [ ] Verify that the "INGREDIENT" names (like "0% Fage Greek Yogurt") still display correctly without excessive wrapping.
- [ ] Confirm the visual spacing between all columns is consistent and improved.
