# 13_IMPLEMENTATION_.md

This plan focuses on reducing the visual spacing between the "Ingredient" and "Grams" columns in the Macros Calculator table on the `Intro` tab.

## User Review Required

> [!NOTE]
> Reducing the spacing is achieved by adjusting the grid column ratios and the horizontal gap between columns. This will bring the numeric inputs closer to the ingredient names, especially on wider screens.

## Proposed Changes

### UI Styling Adjustments

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Update `.table-row` to use a more compact grid layout for the first two columns.
- Change `grid-template-columns` from `2fr 0.8fr 1.2fr 1.2fr` to `1.2fr 0.8fr 1fr 1fr` (or similar) to reduce the empty space after ingredient names.
- Reduce the horizontal `gap` between columns from `15px` to `10px`.

## Verification Plan

### Manual Verification
- [ ] Navigate to the `Intro` tab.
- [ ] Verify that the "Grams" input fields are positioned closer to the "Ingredient" names.
- [ ] Ensure the "Protein" and "Calories" columns still have adequate spacing and alignment.
- [ ] Check the layout on mobile (max-width: 600px) to ensure the media query still looks good (though we might not need to change it if it's already tight).

## Checklist
- [x] Update `.table-row` grid-template-columns in `style.css`.
- [x] Update `.table-row` gap in `style.css`.
- [x] Verify alignment of headers and data rows.
- [x] Test responsiveness.
