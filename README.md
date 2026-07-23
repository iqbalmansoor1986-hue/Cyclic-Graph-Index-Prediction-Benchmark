# Cyclic Graph Index Prediction Benchmark

A reproducible framework for exact topological-index computation, surrogate prediction, transferability analysis, larger-graph stress testing, and split-protocol evaluation across cyclic graph families.

## Overview

This repository provides the implementations associated with a controlled computational framework for generating cyclic graphs, applying valid structure-preserving transformations, computing exact topological indices, and training machine-learning and graph-neural-network models for multi-output regression.

The repository now contains three complementary implementations:

1. **Bounded unicyclic and bicyclic benchmark**  
   Generates simple connected unicyclic and bicyclic graphs, computes exact labels, and compares descriptor-based regressors with graph neural networks.

2. **Circulant transferability and larger sparse-multicyclic experiments**  
   Evaluates transferability to circulant graphs and studies prediction and exact-computation behavior in a larger sparse-multicyclic regime.

3. **Graph-level and parent-aware split analysis**  
   compares conventional graph-level partitioning with parent-aware partitioning to assess whether transformed graphs derived from the same parent graph affect evaluation results.

The framework supports six classical topological indices:

* Wiener index `W(G)`
* Merrifield--Simmons index `MS(G)`
* Hosoya index `Z(G)`
* First Zagreb index `M1(G)`
* Second Zagreb index `M2(G)`
* Randić index `R(G)`

## Main Features

* Controlled generation of unicyclic and bicyclic graph families
* Reconstruction and analysis of circulant graph families
* Generation of larger sparse-multicyclic graphs
* Structure-preserving local graph transformations
* Parent-graph tracking for transformed instances
* Duplicate removal through graph hashing
* Exact computation of six topological indices
* Node-level and graph-level structural feature extraction
* Multi-output regression using:
  * Linear Regression
  * MLP
  * Random Forest
  * GCN
  * GAT
  * GIN
* Graph-level and parent-aware train/validation/test partitions
* Stratification by graph family, graph order, and structural configuration
* Standardized and original-scale performance evaluation
* Corrected original-scale MAPE calculation
* Runtime profiling of exact combinatorial labeling
* Reproducible tables, figures, metadata, and trained-model outputs
