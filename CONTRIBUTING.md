# Contributing

This repository is intentionally small. Contributions should keep the core package easy to install, read, and test.

## Good Contributions

- clearer routing examples
- better smoke tests
- shorter skill wording without losing behavior
- bug reports from real agent sessions
- optional add-ons that stay separate from the v0.1 core

## Keep Out Of Core

- private task histories
- local cache/data folders
- large scraped datasets
- runtime-specific secrets or paths
- heavy research backends unless packaged as optional add-ons

## Validation

Before proposing a change, run through `references/smoke-tests.md` in a fresh agent session and note what passed or failed.
