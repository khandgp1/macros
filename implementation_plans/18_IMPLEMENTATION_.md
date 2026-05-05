# 18_IMPLEMENTATION_ - Narrower Table and Tightened Protein/Calories Spacing

Reduce the visual spacing between the **PROTEIN** and **CALORIES** columns by approximately half, and narrow the overall table container to create a more compact UI.

## Proposed Changes

### Macros Calculator UI

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)

Tighten the proportions for the nutritional data columns and reduce the overall table width.

- **Column Proportion Adjustment**: Adjust `grid-template-columns` to reduce the space allocated to the Protein and Calories columns.
    - **Current**: `grid-template-columns: 1fr 0.3fr 1fr 1fr;`
    - **Proposed**: `grid-template-columns: 1.2fr 0.3fr 0.6fr 0.6fr;` (This pulls the last two columns closer together by reducing their shared percentage of the row).
- **Table Width Adjustment**: Reduce the `max-width` of the macro calculator container to keep the layout compact on wider screens.
    - **Proposed**: Add `max-width: 600px;` to `.macro-calc-container` (or adjust current value if it exists).

## Checklist

- [x] Modify `.table-row` in `style.css` to change `grid-template-columns` to `1.2fr 0.3fr 0.6fr 0.6fr`.
- [x] Update `.macro-calc-container` in `style.css` to set a narrower `max-width` (e.g., `650px` down from current width).
- [ ] Verify that the "PROTEIN" and "CALORIES" headers still fit comfortably without wrapping.
- [ ] Confirm the overall table looks more compact and the spacing is reduced as requested.
