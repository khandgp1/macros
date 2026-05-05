# 19_IMPLEMENTATION_ - Refine Column Spacing and Table Width

Adjust the macros calculator layout to reduce spacing between **INGREDIENT** and **GRAMS**, while adding spacing between **GRAMS** and **PROTEIN**.

## Proposed Changes

### Macros Calculator UI

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)

Refine the grid and add targeted margins to create asymmetrical spacing between columns.

- **Tighten Ingredient/Grams**: Adjust `grid-template-columns` to further reduce the share of the first two columns.
    - **Current**: `grid-template-columns: 1.2fr 0.3fr 0.6fr 0.6fr;`
    - **Proposed**: `grid-template-columns: 1fr 0.25fr 0.6fr 0.6fr;`
- **Add Gap between Grams and Protein**: Add a left margin to the Protein column to push it away from the Grams input.
    - **Proposed**: Add `.col-p { margin-left: 25px; }` (and adjust the header border if needed).
- **Table Width**: Further reduce the table container width for a more focused look.
    - **Proposed**: Change `.macro-calc-container` `max-width` to `600px`.

## Checklist

- [x] Update `.macro-calc-container` in `style.css` to `max-width: 600px`.
- [x] Update `.table-row` in `style.css` to `grid-template-columns: 1fr 0.25fr 0.6fr 0.6fr`.
- [x] Add `margin-left: 25px` to `.col-p` in `style.css` to create the requested spacing between Grams and Protein.
- [ ] Verify the layout across all columns to ensure readability and alignment.
