# AutoPilot

**Declarative GUI testing and automation. One plan, every platform. No LLM in the execution path.**

AutoPilot drives real applications the way a person does — clicking, typing, scrolling, asserting — from a single declarative JSON **plan**. Each platform reimplements the same plan loop natively against its own accessibility API, so a plan is a description of *intent*, not a script of coordinates.

Because there is no language model at runtime, runs are **deterministic and reproducible**: the same plan produces the same result, in CI or on your desk.

## Four platforms, one contract

| Platform | Implementation | Drives |
|---|---|---|
| **macOS** | Swift + Accessibility API | Native macOS apps |
| **iOS** | Swift + XCUITest | Real devices and simulators |
| **Android** | Kotlin + UiAutomator | Real devices and emulators |
| **Web** | TypeScript + Playwright | Any browser page |

The **only** shared artifact is the JSON plan schema. Nothing else crosses platform boundaries — no shared runtime, no lowest-common-denominator abstraction layer.

### Skip, don't branch

Some steps genuinely cannot exist everywhere: there is no menu bar on Android, no native pixel capture in a browser. Rather than forcing plans to fork per platform, a backend that cannot perform a step **skips it and passes**, never errors.

One plan runs everywhere. Skips are reported honestly, so you always know what did and did not execute.

## Your test plan is also your demo script

The same plan that gates your CI can drive a live screencast. Demo steps — `highlight`, `caption`, `pace` — are first-class in the schema, but they are **passing no-ops in a normal test run**, so your tests stay fast and clean.

Turn demo mode on and the plan renders on-screen highlights, narration captions, and human-paced typing, with video capture. Write the flow once; use it as a regression test and as documentation.

## Repositories

| Repository | What it is |
|---|---|
| [`autopilot-core`](https://github.com/TestingAutoPilot/autopilot-core) | Platform-agnostic plan model, parser, and runner. **The schema source of truth.** |
| [`autopilot-macos`](https://github.com/TestingAutoPilot/autopilot-macos) | macOS driver, CLI, and Cockpit GUI |
| [`autopilot-ios`](https://github.com/TestingAutoPilot/autopilot-ios) | iOS runner (XCUITest) |
| [`autopilot-android`](https://github.com/TestingAutoPilot/autopilot-android) | Android runner (UiAutomator) |
| [`autopilot-web`](https://github.com/TestingAutoPilot/autopilot-web) | Web runner (Playwright), published to npm |
| [`homebrew-autopilot`](https://github.com/TestingAutoPilot/homebrew-autopilot) | Homebrew tap for the macOS CLI |

## Cockpit

`autopilot-macos` ships **Cockpit**, a SwiftUI app for working with plans visually: inspect a live accessibility tree, pick elements to build selectors, author plans, and run them with demo mode on or off.

## Getting started

```sh
# macOS CLI
brew tap TestingAutoPilot/autopilot
brew install autopilot

# Web runner
npm install autopilot-web
```

Each repository's own README covers setup, permissions, and usage in full.

---

*AutoPilot is free and open source.*
