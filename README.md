[README.md](https://github.com/user-attachments/files/28872437/README.md)
# Microgrid PV Forecasting Reproducibility Package

This repository provides the reproducibility package for the manuscript:

**Physics-Guided Persistence-Gated Bounded Residual Transformer for Robust and Probabilistic Short-Term Photovoltaic Power Forecasting**

The uploaded file `reproducibility_code_package.zip` contains the preprocessing, dataset-conversion, model-training, evaluation, aggregation, and figure-generation code used in the manuscript experiments.

## Repository Contents

- `reproducibility_code_package.zip`: compressed reproducibility package.
- `experiments/` inside the zip: experiment scripts, model implementations, metrics, reporting utilities, and result aggregation code.
- `experiments/adapters/` inside the zip: conversion scripts for the UCSD, StoreNet, and Bath datasets.
- `experiments/results/` inside the zip: compact CSV summaries and LaTeX result tables used to regenerate the manuscript tables and figures.
- `data/processed/*.metadata.json` inside the zip: metadata files produced by the dataset adapters.

The raw public datasets are not redistributed in this repository. They should be downloaded from the original public sources listed below.

## Public Data Sources

- UCSD Microgrid Database: <https://github.com/sushilsilwal3/UCSD-Microgrid-Database>
- UCSD data descriptor: <https://doi.org/10.1063/5.0038650>
- StoreNet energy-community dataset: <https://doi.org/10.6084/m9.figshare.c.6829134>
- University of Bath PV-battery microgrid dataset: <https://doi.org/10.15125/BATH-01287>

## How to Use

1. Download `reproducibility_code_package.zip`.
2. Extract the archive.
3. Install the required Python packages:

```bash
pip install -r experiments/requirements.txt
```

4. Regenerate converted datasets using the adapter scripts in `experiments/adapters/`.
5. Run the experiment scripts described in `experiments/README.md`.
6. Use `experiments/aggregate_results.py` and `experiments/plot_paper_figures.py` to regenerate the reported tables and figures.

## Main Scripts

- `experiments/adapters/convert_ucsd.py`: converts the UCSD campus microgrid data.
- `experiments/adapters/convert_storenet.py`: converts the StoreNet energy-community data.
- `experiments/adapters/convert_bath.py`: converts the Bath PV-battery microgrid data.
- `experiments/run_experiments.py`: runs deterministic forecasting experiments.
- `experiments/evaluate_ensemble.py`: evaluates ensemble and conformal prediction intervals.
- `experiments/aggregate_results.py`: aggregates result CSV files into manuscript-ready tables.
- `experiments/plot_paper_figures.py`: regenerates manuscript figures.

## Notes

The public-data experiments use chronological splits and fixed random seeds as described in the manuscript. For computational tractability, some large-dataset baselines use a documented subsampling rule for training windows. These settings are recorded in the scripts and result files.

## Citation

If this repository is used, please cite the associated manuscript and the original public datasets listed above.
