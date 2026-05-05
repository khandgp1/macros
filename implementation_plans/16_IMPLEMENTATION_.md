# 16_IMPLEMENTATION_ - Reduce Column Spacing in Macros Calculator

Reduce the visual spacing between the **INGREDIENT** column and the **GRAMS** column in the macros calculator on the `Intro` tab.

## Proposed Changes

### Macros Calculator UI

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)

Adjust the `grid-template-columns` property for `.table-row` to reduce the proportion of the first two columns, bringing them closer together.

- **Current**: `grid-template-columns: 1.2fr 0.8fr 1fr 1fr;`
- **Proposed**: `grid-template-columns: 1fr 0.4fr 1fr 1fr;` (This tightens the space allocated to the ingredient name and the grams input, reducing the perceived gap.)

## Checklist

- [x] Modify `.table-row` in `style.css` to adjust `grid-template-columns`.
- [ ] Verify the layout on the `Intro` tab to ensure ingredient names still fit and the spacing is reduced as requested.
- [ ] Ensure the alignment of other columns (Protein, Calories) remains consistent.
