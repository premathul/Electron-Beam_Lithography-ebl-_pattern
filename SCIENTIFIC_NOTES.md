# Scientific and Engineering Notes

## Geometry definitions

For two adjacent circular holes with center coordinates `x_(i-1)` and `x_i`, and diameters `d_(i-1)` and `d_i`:

- Center-to-center spacing: `c2c_i = x_i - x_(i-1)` after sorting by position.
- Edge-to-edge gap: `g_i = c2c_i - (d_i + d_(i-1))/2`.

A negative edge gap indicates geometric overlap in the 1D centerline model.

## What a flag means

A flag means the geometry meets a numerical review condition. It does **not** by itself mean the structure is un-fabricable. Minimum feature/gap limits depend on resist stack, substrate, acceleration voltage, beam current, dose, development, pattern density, PEC, etch/lift-off transfer, and tool calibration.

## Taper check

The diameter-step check evaluates `|d_i - d_(i-1)|` against a user-selected threshold. It is intended to catch transcription errors or unexpectedly abrupt taper changes. It is not a physical adiabaticity criterion.

## Recommended validation chain

1. Check numerical geometry here.
2. Inspect the complete CAD layout and units.
3. Run any required PEC/fracturing workflow.
4. Confirm minimum features against the facility's current process window.
5. Fabricate/test dose or process matrices where needed.
6. Verify critical dimensions by appropriate metrology.

## Current assumptions

- One-dimensional ordered center coordinates.
- Circular holes represented by scalar diameters.
- Nanometers are used for all numeric dimensions.
- Only nearest-neighbor geometry is evaluated.
