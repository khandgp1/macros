# 15_IMPLEMENTATION_.md

This plan focuses on further tightening the visual layout of the Macros Calculator table by reducing specific column spacings.

## User Review Required

> [!NOTE]
> We are reducing the spacing specifically between the "Ingredient/Grams" pair and the "Protein/Calories" pair. This is achieved by adjusting the grid column ratios to be more asymmetrical and further reducing the horizontal gap.

## Proposed Changes

### UI Styling Adjustments

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)
- Update `.table-row` grid-template-columns to `1.5fr 0.6fr 1.2fr 0.6fr`.
- Reduce the horizontal `gap` from `10px` to `8px` (or `6px` if needed) to bring content even closer.
- Ensure that the "Calories" header doesn't wrap or overlap by checking text-overflow if necessary.

## Verification Plan

### Manual Verification
- [ ] Navigate to the `Intro` tab.
- [ ] Verify that the "Grams" input is tucked closer to the "Ingredient" name.
- [ ] Verify that the "Calories" value is tucked closer to the "Protein" value.
- [ ] Check for any text overlapping, especially with the longer header names like "CALORIES".
- [ ] Verify responsiveness on smaller screens.

## Checklist
- [ ] Update `.table-row` grid-template-columns in `style.css`.
- [ ] Update `.table-row` gap in `style.css`.
- [ ] Test alignment and readability.
