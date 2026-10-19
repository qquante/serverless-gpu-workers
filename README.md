# Serverless GPU Workers

Experimental Modal GPU worker definitions for containerized mining workloads and operational logging.

![review](https://img.shields.io/badge/review-private-374151) ![primary](https://img.shields.io/badge/primary-Python-2563EB) [![LinkedIn](https://img.shields.io/badge/LinkedIn-Douglas%20Silva-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/douglas-silva-data-analyst/)

[Overview](#overview) · [Architecture](#architecture) · [Setup](#setup) · [Validation](#validation) · [Roadmap](#roadmap) · [Review notes](docs/REVIEW.md)

## Overview

- Python definitions describe GPU images and worker execution.
- Separate pool adapters capture environment-specific configurations.
- Original and copied local variants are retained for comparison.

**Technology:** Python · Modal · GPU container images · worker/pool integrations

**Persistence and data:** Worker logs and provider state live in the configured cloud/runtime environment; no local database is bundled.

## Architecture

```text
Local Modal definition → configured GPU container → worker/pool process → provider logs
```

| Location | Review focus |
| --- | --- |
| [`modal-pearl/akoya_modal.py`](modal-pearl/akoya_modal.py) | Source/configuration inspected for scope and structure |
| [`modal-pearl/pearlhash_modal.py`](modal-pearl/pearlhash_modal.py) | Source/configuration inspected for scope and structure |
| [`modal-pearl - Copia`](modal-pearl%20-%20Copia) | Source/configuration inspected for scope and structure |

Internal package and module names are retained where changing them would affect imports or compatibility. This descriptive repository name does not imply a completed package/API migration.

## Setup

Inspect definitions offline. Do not run modal deploy or modal run to review source; cloud authentication and paid execution are separate operational actions.

Start from an isolated environment. Use `.env.example` when present and inspect the configuration loader: an example file is not necessarily loaded automatically. Runtime databases, real account sessions and private credentials are not bundled. Live integration prerequisites are separate from local tests.

## Validation

Static parsing checked 4 Python files and 0 strict JSON files. Python syntax errors: 0; JSON errors: 0. No functional test/build result is claimed for this preparation.

Available test scripts are inventoried in [the review notes](docs/REVIEW.md). Choose offline checks before operating any integration.

These results apply to the selected checks on the preparation copy. They do not establish deployment readiness, full coverage, live provider availability or measured performance. CI definitions, when present under `docs/ci-templates/`, are inactive review templates; no remote CI badge is claimed.

## Limits and current status

Deploying these definitions can allocate billable GPUs. No cloud deployment or mining process was started. Historical hashrate numbers are not verified measurements in this review.

This private snapshot is for code and portfolio review. Generated runtime material and unreviewed binary assets may be excluded. [Review notes](docs/REVIEW.md) record preparation scope, findings and outstanding validation.

## Roadmap

- [ ] Compare duplicate folders and select a canonical definition.
- [ ] Move wallet/pool identifiers into explicit local configuration.
- [ ] Review provider rules, costs and shutdown limits before any deployment.

## History and attribution

No recoverable original Git history was verified for this snapshot. Import and preparation commits use their actual current dates; filesystem timestamps are not treated as development dates.

No open-source license is granted by this preparation. A license and attribution review is required before public redistribution.

## Maintainer and feedback

Douglas de Oliveira Silva · [GitHub](https://github.com/qquante) · [LinkedIn](https://www.linkedin.com/in/douglas-silva-data-analyst/)

For this private review, report reproducible issues with a minimal fixture and the exact check output. Keep account data, credentials and generated sensitive reports out of issues and commits. Existing contribution guidelines apply where present.

**Topics:** `python`, `modal`, `gpu`, `serverless`, `docker`, `infrastructure`
