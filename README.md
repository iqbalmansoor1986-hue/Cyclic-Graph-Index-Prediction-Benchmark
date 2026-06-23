# Cyclic-Graph-Index-Prediction-Benchmark
A reproducible benchmark framework for exact topological-index labeling and surrogate prediction on synthetic unicyclic and bicyclic graph families.

# Cyclic Graph Index Prediction Benchmark

A reproducible benchmark framework for exact topological-index labeling and surrogate prediction on synthetic unicyclic and bicyclic graph families.

## Overview

This repository contains the implementation of a controlled computational pipeline for generating synthetic cyclic graphs, applying structure-preserving transformations, computing exact topological indices, and training machine learning and graph neural network models for multi-output regression. The framework is designed as a reproducible benchmark for studying topological-index prediction under controlled graph-family constraints.

The current implementation focuses on simple connected **unicyclic** and **bicyclic** graphs with bounded order and supports six classical topological indices:

* Wiener index `W(G)`
* Merrifield--Simmons index `MS(G)`
* Hosoya index `Z(G)`
* First Zagreb index `M1(G)`
* Second Zagreb index `M2(G)`
* Randić index `R(G)`

## Main Features

* Synthetic generation of unicyclic and bicyclic graph families
* Structure-preserving local graph transformations
* Duplicate removal through graph hashing
* Exact combinatorial labeling of six topological indices
* Node-level structural feature extraction
* Multi-output regression using:

  * Linear Regression
  * MLP
  * Random Forest
  * GCN
  * GAT
  * GIN
* Stratified train/validation/test splitting
* Standardized multi-target evaluation
* Reproducible tables, figures, and trained model outputs

## Repository Structure

```text
.
├── notebooks/
│   └── Unicyclic_and_Bicyclic_MDPI_paper_Implementation.ipynb
├── outputs/
│   ├── figures/
│   ├── tables/
│   ├── metadata/
│   └── models/
├── requirements.txt
├── environment.yml
└── README.md
```

## Methodology Summary

The benchmark pipeline consists of the following stages:

1. Generate synthetic unicyclic and bicyclic graphs over a bounded graph-order range
2. Remove duplicate graph instances using graph hashing
3. Apply valid local structure-preserving transformations
4. Compute exact target labels for all graphs
5. Extract node-level and graph-level features
6. Construct train, validation, and test splits using stratification by graph family and graph order
7. Train baseline regressors and graph neural network models
8. Evaluate performance on standardized and index-wise scales
9. Export reproducible tables, figures, and trained models

## Experimental Setting

The implementation was developed and tested in **Google Colab** with **T4 GPU** enabled for graph neural network training. Exact labeling is performed offline, while trained inference is used for repeated-query prediction.

## Installation

### Option 1: pip

```bash
pip install -r requirements.txt
```

### Option 2: conda

```bash
conda env create -f environment.yml
conda activate cyclic-graph-benchmark
```

## Core Dependencies

Typical dependencies include:

* Python 3.11+
* numpy
* pandas
* matplotlib
* networkx
* scikit-learn
* torch
* torch-geometric
* joblib

## Running the Notebook

Open the notebook in Jupyter or Google Colab and run all cells from top to bottom:

```text
notebooks/Unicyclic_and_Bicyclic_MDPI_paper_Implementation.ipynb
```

Recommended runtime setting for Colab:

* Runtime type: **GPU**
* GPU: **T4**

## Outputs

The pipeline exports:

* target statistics tables
* overall model-comparison tables
* index-wise and family-wise evaluation tables
* runtime analysis tables
* manuscript-ready figures
* trained model weights
* dataset split files
* fitted scalers
* runtime and configuration summaries

## Important Notes

* The benchmark is intentionally **controlled** and is not intended to replace exact computation in all small-graph settings.
* Descriptor-based baselines can be very strong in this restricted setting because handcrafted summaries already capture a large fraction of structural variation.
* Among the graph-native models, **GIN** provides the strongest overall graph neural network performance in the current implementation.
* Aggregate multi-target errors are reported on a standardized target scale, while target-specific interpretation is supported through per-index results and original-scale descriptive statistics.

## Limitations

* The dataset is synthetic rather than domain-specific
* The framework is currently limited to simple connected unicyclic and bicyclic graphs
* Exact computation of combinatorial indices remains an offline cost
* Direct transfer to larger multicyclic or domain-specific graphs requires additional generation and labeling procedures

## Future Extensions

Possible extensions include:

* evaluation on molecular and network datasets
* support for larger multicyclic graph families
* uncertainty-aware regression
* more expressive graph-learning architectures
* transfer learning from synthetic to domain-specific graph benchmarks

## Citation

If you use this repository, please cite the associated paper once available.

```bibtex
@article{cyclic_graph_benchmark,
  title={A reproducible benchmark framework for topological-index prediction on unicyclic and bicyclic graphs},
  author={Author Names},
  journal={Algorithms},
  year={2026}
}
```

## License

Add your preferred license here, for example:

```text
MIT License
```
