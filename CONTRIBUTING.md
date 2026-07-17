# Contributing to AutoPilot

AutoPilot is a declarative GUI-test and automation driver: one JSON **plan** (no LLM in
the execution path) drives real applications through each platform's accessibility API.
[`autopilot-core`](https://github.com/TestingAutoPilot/autopilot-core) owns the plan
schema; the macOS, iOS, Android, and web runners each reimplement the same plan loop
natively. The **only** shared contract is the JSON plan schema.

## Before you propose

- **The schema is the one shared contract.** A new action or argument lands in
  `autopilot-core` **first** (the Swift plan model *and* `plan.schema.json`), then each
  runner mirrors it. A change that starts in one runner and skips core will drift.
- **Skip, don't branch.** A backend that cannot perform a step **skips it and passes** —
  it never errors and the plan never forks per platform. One plan runs everywhere; skips
  are reported honestly.
- **Stay backward compatible.** An existing plan must keep parsing and running. New
  actions are additive; demo steps are passing no-ops in a normal test run.

## How

1. Open an issue describing the change **and which repos / platforms it touches**.
2. Write a **failing test first**, then the minimal code to pass it. Keep commits small
   and focused.
3. Make provenance explicit: mark what is verified, what is documented, and what is
   assumed.

## Licensing

Each repository states its own license (for example, `autopilot-web` is MIT). By
contributing, you agree your contribution is licensed under that repository's license.
