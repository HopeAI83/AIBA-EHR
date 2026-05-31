# AIBA-EHR Reproducibility Package

This repository provides the minimal public reproducibility package for the manuscript:

**AI-Accelerated Blockchain Architecture for Efficient and Secure Electronic Healthcare Record Exchange**

Submission ID: `b0d8734d-aa17-4036-b6d0-57cecdbfc94f`

The repository is intentionally kept as a **single-folder upload**. All code, data, result tables, and figures are stored directly in the repository root.

## Contents

### Required editor-requested components

| Component requested by editor | File(s) included |
|---|---|
| ChainSimEnv environment | `chainsim_env.py` |
| PPO agent | `ppo_agent.py` |
| TCN+AM module | `tcn_attention_model.py` |
| Synthetic dataset of 120,000 access events | `synthetic_ehr_access_events_120000.csv` |

### Core data files

- `synthetic_ehr_access_events_120000.csv` — synthetic EHR access-event dataset with 120,000 rows.
- `data_dictionary.csv` — field-level description of the dataset.
- `cv_fold_assignments.csv` — fold assignments for reproducible cross-validation.
- `SHA256SUMS.txt` — checksum manifest.

No real patient data, protected health information, identifiable health information, or human-subject data are included.

### Core code files

- `config.py` — global seed, TCN, PPO, reward, and simulation configuration.
- `data_generator.py` — deterministic synthetic data generator.
- `preprocessing.py` — preprocessing utilities.
- `tcn_attention_model.py` — TCN with attention module.
- `chainsim_env.py` — blockchain simulation environment.
- `ppo_agent.py` — PPO agent configuration wrapper.
- `evaluation.py` — metric and McNemar-test utilities.
- `reproduce_all_results.py` — regenerates principal result tables and figures.
- `verify_repository_readiness.py` — checks that all mandatory files are present and the dataset has 120,000 rows.

## Installation

```bash
pip install -r requirements.txt
```

## Verification

Run the repository readiness check:

```bash
python verify_repository_readiness.py
```

Expected output:

```text
Repository readiness check PASSED
Dataset rows: 120000
```

## Reproducing selected result files

```bash
python reproduce_all_results.py
```

This regenerates the principal result tables and figures in the same folder.

## Important reproducibility note

This package is a public synthetic-data reproducibility package. It is designed to allow inspection of the ChainSimEnv simulator, PPO configuration, TCN+AM module, dataset structure, result tables, and reproduced figures associated with the revised manuscript. The dataset is synthetic and does not contain real patient records or identifiable health information.

## Recommended manuscript availability statement

```latex
\bmhead{Data Availability}

The synthetic Electronic Healthcare Record (EHR) access-event dataset used for the public reproducibility package of this study, comprising 120,000 access events, the data dictionary, cross-validation fold assignments, and checksum manifest, is available in the public GitHub repository at: \url{https://github.com/HopeAI83/AIBA}. No real patient data, protected health information, identifiable health information, or human-subject data were used in this study.

\bmhead{Code Availability}

The complete Python implementation required to inspect and reproduce the experiments reported in this manuscript is available in the public GitHub repository at: \url{https://github.com/HopeAI83/AIBA}. The repository includes the ChainSimEnv blockchain simulation environment, the PPO-based reinforcement learning agent, the TCN+AM anomaly detection module, synthetic data-generation script, result tables, reproduced figures, and verification scripts.
```
