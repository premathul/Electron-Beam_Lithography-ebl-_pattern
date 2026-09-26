# Contributing

Contributions should preserve the project's local-first behavior and dimensional clarity.

Before submitting a change:

1. Test parsing with CSV and tab-separated input.
2. Verify center-to-center and edge-gap calculations by hand for a small pattern.
3. Test duplicate centers, overlaps, sub-threshold gaps, and abrupt diameter changes.
4. Confirm CSV export reproduces the displayed calculated values.
5. Avoid adding network dependencies unless there is a clear engineering reason.

For scientific changes, document assumptions and units in `SCIENTIFIC_NOTES.md`.
