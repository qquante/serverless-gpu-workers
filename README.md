# Serverless GPU Workers

![Language: Python](https://img.shields.io/badge/Language-Python-3776AB?style=flat-square&logo=python) ![Provider: Modal](https://img.shields.io/badge/Provider-Modal-555555?style=flat-square) [![License: MIT](https://img.shields.io/badge/License-MIT-555555?style=flat-square)](LICENSE)

Two experimental Modal GPU workload definitions for mining-worker containers. This repository contains deployment code and process wiring, not a measured GPU-performance report.

## Compare the definitions

| Definition | GPU setting | Container/process behavior |
| --- | --- | --- |
| [akoya_modal.py](modal-pearl/akoya_modal.py) | `H100` | Uses the Akoya registry image, selects a GEMM library from detected compute capability, then replaces the process with the miner. |
| [pearlhash_modal.py](modal-pearl/pearlhash_modal.py) | `A100-80GB` | Builds on a CUDA runtime image, downloads a miner executable and streams its process output. |

Both definitions expose a local entrypoint that invokes a remote GPU function. Wallet/worker/pool settings are currently source-level inputs; inspect and replace them before any deployment. A payout address is not a private key, but it still determines where work is credited.

## Inspect without allocating a GPU

```console
python -m py_compile modal-pearl/akoya_modal.py modal-pearl/pearlhash_modal.py
```

This compiles Python syntax without importing the Modal SDK or launching the functions. There is no dedicated offline workload test suite.

Running `modal run` or `modal deploy` is a separate billable operational step requiring your Modal account, current provider availability and review of the referenced third-party images/binary. The source uses moving image/download references, so identical deployment inputs do not guarantee reproducible binaries. No current hashrate, cost advantage or profitability is claimed.

**Technology:** Python · Modal · GPU container images · worker/pool integrations

Project-authored source: [MIT](LICENSE). Third-party components retain their own notices and terms.
