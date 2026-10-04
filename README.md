# SyntheticTab

**Generative Models for Synthetic Tabular Data: Fidelity, Utility, Diversity and Privacy**

SyntheticTab is a research-oriented machine-learning project for studying generative models of synthetic tabular data. It will compare several families of generative models on the same real-world tabular data, looking at how closely the synthetic data matches the real data statistically, how useful it is for training downstream models, how much of the real data distribution it covers, how much empirical privacy risk it carries, and how much it costs to compute. The project will also look at how the amount of training data affects the performance of each generative model.

> **Status:** initial repository setup. Nothing beyond the project scaffolding has been implemented yet. See [Current development status](#current-development-status).

## Objectives

- Set up a reproducible codebase for training and sampling from several tabular generative models under a common interface.
- Compare these models across the evaluation dimensions listed below.
- Study how training-data size affects generative-model performance.
- Document datasets, preprocessing decisions and experimental settings clearly enough that results can be reproduced.

## Planned model families

These are the model families the project plans to study first. **None of them has been implemented yet.**

1. **Vine Copula**: a statistical model built from pairwise copulas.
2. **CTGAN**: a conditional generative adversarial network for tabular data.
3. **TVAE**: a variational autoencoder for tabular data.
4. **TabDDPM**: a denoising diffusion probabilistic model for tabular data.

## Planned evaluation dimensions

These dimensions are planned. Specific metrics have not been chosen or implemented yet.

- **Statistical fidelity**: how closely the synthetic data reproduces the marginal distributions and dependencies of the real data.
- **Downstream ML utility**: how well models trained on synthetic data do on real held-out data, compared with models trained on real data.
- **Distributional coverage**: whether the synthetic data covers the whole range of the real data, including rare categories and less common regions, rather than only part of it.
- **Empirical privacy risk**: how much information about individual training records the synthetic data may reveal, measured empirically. Synthetic data is not assumed to be private by default, and the project does not aim to provide formal privacy guarantees.
- **Computational cost**: the time and resources needed to train each model and to generate samples.

Training-data size will be varied as an experimental factor across these dimensions.

## Repository structure

```
SyntheticTab/
├── configs/        # Experiment and model configuration files
├── data/           # Local data (not committed; see data/README.md)
│   ├── raw/
│   └── processed/
├── src/                # Source directory
│   └── synthetictab/   # Python package
│       ├── data/       # Data loading and preprocessing
│       ├── models/     # Generative model wrappers
│       ├── training/   # Training routines
│       ├── generation/ # Sampling synthetic data
│       ├── evaluation/ # Evaluation code
│       └── utils/      # Shared helpers
├── notebooks/      # Exploratory notebooks
├── experiments/    # Experiment definitions and scripts
├── results/        # Generated outputs (not committed by default)
├── research/       # Notes and literature
├── tests/          # Tests
└── app/            # Reserved for a possible future application
```

## Setup

Requires Python 3.10 or later.

```bash
python -m venv .venv
# Windows
.venv\Scripts\activate
# macOS / Linux
source .venv/bin/activate

pip install -r requirements.txt
pip install -e .
```

Model-specific dependencies will be added once the implementation choices are made.

## Current development status

The project is in its **initial repository and setup phase**.

**Implemented**

- Repository structure and Python package skeleton (`src/`)
- Basic project configuration (`pyproject.toml`, `requirements.txt`, `.gitignore`)

**Not yet done**

- The final dataset has not been selected.
- The models have not been implemented.
- The evaluation has not been implemented.
- No experiments have been run, so there are no results yet.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE).
