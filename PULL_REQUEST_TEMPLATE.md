## What & why

<!-- What does this change, and why? Link the issue. -->

## If this touches the plan schema (a contract)

- [ ] Landed in `autopilot-core` **first** — the Swift plan model *and* `plan.schema.json`
- [ ] Each affected runner mirrors it (macOS / iOS / Android / web)
- [ ] **Backward compatible** — existing plans still parse and run
- [ ] **Skip, don't branch** — backends that can't perform the step skip it (passing),
      never error

## Tests

- [ ] A **failing test first**, then the minimal code to pass it
- [ ] Cross-platform parity checked where the change spans backends

## Record

- [ ] Status and provenance are explicit (verified / documented / assumed)
