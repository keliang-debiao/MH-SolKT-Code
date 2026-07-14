# MH-SolKT Code Package

This repository contains the code package for the MH-SolKT sight-singing knowledge tracing study. It provides model implementations, experiment configurations, execution scripts, evaluation utilities, reviewer-check artifacts, and audit tools. This README only describes the contents of the package and does not report experimental results.

## Package Contents

### Source Code

The `src/mhsolkt/` directory contains the Python source code for the project.

- `src/mhsolkt/models/` contains the MH-SolKT framework, model components, baseline model implementations, and model registry.
- `src/mhsolkt/data/` contains dataset loading, preprocessing helpers, graph construction utilities, split construction utilities, schema definitions, and toy-data utilities.
- `src/mhsolkt/training/` contains the training engine, loss functions, checkpoint utilities, and training-related helpers.
- `src/mhsolkt/evaluation/` contains metric computation, calibration analysis, uncertainty analysis, intervention-oriented evaluation, efficiency analysis, and paired-statistics utilities.
- `src/mhsolkt/experiments/` contains experiment manifest and runner utilities.
- `src/mhsolkt/utils/` contains general utilities for input/output handling, device selection, and random-seed control.

### Configuration Files

The `configs/` directory contains YAML configuration files for the experiments.

- `configs/common.yaml` defines shared training, data, and evaluation settings.
- `configs/proposed/` contains configurations for the proposed MH-SolKT variants.
- `configs/baselines/` contains configurations for reproduced knowledge tracing baselines.
- `configs/ablations/` contains configurations for component-removal and single-branch ablation studies.
- `configs/sensitivity/` contains configurations for Mamba implementation, hidden-size, and sequence-length sensitivity experiments.
- `configs/calibration/` contains configurations for calibration-related variants.
- `configs/protocols/` contains configurations for protocol-robustness experiments.
- `configs/intervention/` contains configurations for top-risk intervention analysis.
- `configs/efficiency/` contains configurations for parameter and runtime analysis.
- `configs/smoke/` contains smoke-test and toy-run configurations.
- `configs/tuning_grids/` contains predefined validation-only hyperparameter grids.

### Scripts

The `scripts/` directory contains command-line scripts for preprocessing, running experiments, aggregating outputs, auditing statistics, and exporting reviewer materials.

- `preprocess_singpad.py` prepares raw SingPAD/SingKT records for model training.
- `make_splits.py` creates train, validation, and test splits.
- `run_primary.py` runs the main proposed-framework and baseline experiments.
- `run_ablations.py` runs ablation experiments.
- `run_mamba_sensitivity.py` runs fallback and official-kernel sensitivity experiments.
- `run_hidden_length_sensitivity.py` runs hidden-size and sequence-length sensitivity experiments.
- `run_calibration.py` runs calibration-related experiments.
- `run_uncertainty.py` runs uncertainty-error alignment analysis.
- `run_intervention.py` runs top-risk intervention analysis.
- `run_protocol_robustness.py` runs protocol-robustness experiments.
- `run_efficiency.py` runs parameter and runtime analysis.
- `run_training_trajectory.py` exports training-trajectory materials.
- `run_hyperparameter_search.py` runs validation-only hyperparameter selection.
- `verify_tuning_selection.py` checks hyperparameter-selection records.
- `aggregate_all.py` aggregates per-run outputs into summary files.
- `aggregate_protocol_fivefold.py` performs two-level aggregation for student-wise five-fold outputs.
- `audit_seed_statistics.py` audits the seed-level source file and paired AUC statistics.
- `check_official_mamba_environment.py` checks the official Mamba environment.
- `verify_reviewer_completeness.py` checks whether the expected reviewer artifacts are present.
- `hash_reviewer_artifacts.py` generates file hashes for reviewer artifacts.
- `export_reviewer_artifacts.py` exports selected artifacts for reviewer inspection.
- `plot_experiment_figures.py` generates figure materials from experiment outputs.
- `run_smoke_toy.py` runs a small toy pipeline for code-path verification.

### Data Directories

The `data/` directory provides the expected data layout.

- `data/raw/` is the expected location for raw SingPAD/SingKT files.
- `data/processed/` is the expected location for processed sequence files.
- `data/splits/` is the expected location for split manifests and split files.

The raw SingPAD/SingKT dataset is not redistributed in this package. The data directories are included as placeholders for locally available authorized data.

### Output and Reviewer Artifact Directories

The `outputs/` directory contains or receives run outputs and reviewer-check materials.

- `outputs/primary/` stores main experiment outputs.
- `outputs/ablations/` stores ablation experiment outputs.
- `outputs/mamba_sensitivity/` stores fallback and official-kernel sensitivity outputs.
- `outputs/hidden_length_sensitivity/` stores hidden-size and sequence-length sensitivity outputs.
- `outputs/calibration/` stores calibration experiment outputs.
- `outputs/uncertainty/` stores uncertainty-error alignment outputs.
- `outputs/intervention/` stores top-risk intervention outputs.
- `outputs/protocol_robustness/` stores protocol-robustness outputs.
- `outputs/efficiency/` stores efficiency-analysis outputs.
- `outputs/training_trajectory/` stores training-trajectory outputs.
- `outputs/aggregated/` stores aggregated CSV files.
- `outputs/audit/` stores audit reports.
- `outputs/SHA256SUMS.txt` stores file hashes for checking artifact integrity.

Run-level folders may contain resolved configurations, environment records, training histories, validation histories, checkpoint metadata, final metrics, predictions, and provenance files.

### Tests and Validation

The `tests/` directory contains unit tests for key code paths, including model execution, split behavior, paired-statistics auditing, and auxiliary-head training behavior.

The repository also includes:

- `validate_package.py` for package-structure validation.
- `pytest.ini` for test configuration.
- `pyproject.toml` for package metadata.
- `Makefile` for common workflow commands.

### Environment Files

The package includes environment and dependency files.

- `requirements.txt` lists core dependencies.
- `requirements-dev.txt` lists development and testing dependencies.
- `requirements-official-mamba.txt` lists dependencies for the official Mamba kernel environment.
- `environment-primary.yml` defines the primary environment.
- `environment-official-mamba.yml` defines the official-kernel sensitivity environment.

### Documentation Files

The package includes documentation describing the artifact contract, data schema, implementation notes, package contents, reviewer materials, and compliance checks.

- `ARTIFACT_CONTRACT.md`
- `DATA_SCHEMA.md`
- `MODEL_IMPLEMENTATION_NOTES.md`
- `PACKAGE_MANIFEST.txt`
- `PACKAGE_NOTES.md`
- `REPRODUCTION_CHECKLIST.md`
- `REVIEWER_ARTIFACTS.md`
- `REVIEWER_COMPLIANCE_MATRIX.md`

## Notes

This package is intended to organize the source code, configurations, scripts, and reviewer-check materials for the MH-SolKT study. It does not include the raw SingPAD/SingKT dataset. Any regenerated outputs depend on locally available authorized data and the specified software environment.
