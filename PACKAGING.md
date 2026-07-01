# Packaging Notes

This file is for maintainers preparing the package for public release.

## Include In v0.1

- `skills/deep-research/SKILL.md`
- `skills/grillme/SKILL.md`
- `references/research-layer-v2.md`
- `references/routing-contract.md`
- `references/smoke-tests.md`
- `examples/`
- `README.md`
- `LICENSE`
- `.gitignore`

## Exclude From v0.1

- local task memory
- private workspace paths
- harvested data
- PDF/full-text caches
- `.git`, `.claude`, `.codex`
- `__pycache__`, `*.pyc`, `*.bak`
- heavyweight research backends unless cleaned as separate add-ons

## Optional Future Add-Ons

- source/material intake
- GitHub project harvesting
- web scraping
- competitive research templates
- academic paper discovery/screening/reading
- survey writing

These should be separate packages because they may require runtime-specific tools, API keys, local dependencies, or private data cleanup.
