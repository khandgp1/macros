# 20_IMPLEMENTATION_ - Center Protein Header with Content

Ensure the **PROTEIN** column header is perfectly centered with the numeric data below it.

## Proposed Changes

### Macros Calculator UI

#### [MODIFY] [style.css](file:///Users/khandpv1/Desktop/.AntiGrav/macros/style.css)

Remove the asymmetrical border in the header and synchronize alignment properties.

- **Remove Header Border**: Remove the `border-left` from `.table-row.header .col-p`. This border was only present in the header row, which could cause a subtle visual misalignment of the "PROTEIN" text relative to the data columns below.
- **Synchronize Alignment**: Explicitly ensure `text-align: center` is applied consistently to all parts of the `.col-p` and `.col-c` columns.

## Checklist

- [x] Remove `border-left` from `.table-row.header .col-p` in `style.css`.
- [ ] Verify that the "PROTEIN" header text is visually centered directly above the numbers in the ingredient rows.
- [ ] Confirm that the "CALORIES" header also remains correctly aligned.
- [ ] Ensure the overall table structure remains clean and the new spacing between columns is preserved.
