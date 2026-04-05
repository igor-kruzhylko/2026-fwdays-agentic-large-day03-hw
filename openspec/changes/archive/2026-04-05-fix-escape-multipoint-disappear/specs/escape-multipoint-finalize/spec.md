## ADDED Requirements

### Requirement: Multi-point Escape scenarios are covered by automated tests
The automated test suite SHALL include coverage for multi-point line Escape in both the single committed point case and the two-or-more committed points (finalize) case, so regressions that remove a valid multi-point element on Escape are caught.

#### Scenario: Test asserts Escape after one committed point discards invalid geometry
- **WHEN** the test suite runs multi-point line creation tests
- **THEN** a test SHALL simulate one click to commit the first point, press Escape, and assert the in-progress element is removed or marked deleted and is not left as a visible single-point line

#### Scenario: Test asserts Escape after two or more committed points preserves the line
- **WHEN** the test suite runs multi-point line creation tests
- **THEN** a test SHALL simulate at least two committed points, press Escape, and assert the line remains in the scene with `isDeleted === false` and at least two points
