# Serverless GPU Workers

Experimental Modal GPU worker definitions for containerized mining workloads and operational logging.

## Features

- Python definitions describe GPU images and worker execution.
- Separate pool adapters capture environment-specific configurations.
- Original and copied local variants are retained for comparison.

## Stack

Python · Modal · GPU container images · worker/pool integrations

Worker logs and provider state live in the configured cloud/runtime environment; no local database is bundled.

## Getting started

Inspect definitions offline. Do not run modal deploy or modal run to review source; cloud authentication and paid execution are separate operational actions.

## How it works

```text
Local Modal definition → configured GPU container → worker/pool process → provider logs
```

## Current limitations

Deploying these definitions can allocate billable GPUs. No cloud deployment or mining process was started. Historical hashrate numbers are not verified measurements in this review.

## License

No open-source license has been granted. Redistribution terms remain to be defined.
