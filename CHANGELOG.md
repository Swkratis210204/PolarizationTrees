# Changelog

## [0.2.0]
### Changed
- `scale`, `toxic_range`, `civil_range`, and `neutral_range` are now mandatory arguments to `AnnotatorPool.__init__` — there are no longer default values for any of them. **This is a breaking change**: code that previously called `AnnotatorPool(dimensions)` without these arguments will now raise a `TypeError`.

### Added
- Moderate and Low tier toxic/civil ranges are now derived automatically from the user-supplied `toxic_range`, `civil_range`, and `scale`, instead of being hardcoded for a 1–5 scale. The derivation shifts each range toward the center by a step proportional to `scale`, so it generalizes correctly to any rating scale.
- `AnnotatorPool.summary()` now prints the derived Moderate and Low ranges alongside the High tier's ranges.