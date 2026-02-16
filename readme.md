# Detect, Adapt, Overcome: Mitigating Concept Drift in Federated Learning

This repository contains experiments for concept drift detection and adaptation in Federated Learning using the MNIST dataset and CNN models.

The project investigates how distributed models behave when local client data distributions change over time and proposes detection and adaptation strategies.

## 1. Project Overview

This project explores:

- Federated learning with multiple clients

- Concept drift scenarios

- Detection algorithms for drift

- Adaptation strategies to maintain model performance

It focuses on three drift types:

- Sudden drift (sdrift)

- Gradual/incremental drift (gdrift)

- Hybrid drift (mix)

The experiments analyze detection accuracy, loss behavior, and adaptation performance across clients.


## 2. Key Objectives

**Detection**

Detect when a client’s local data distribution changes.

**Adaptation**

Improve model performance after drift by adapting global or local models.

**Evaluation**

**Measure:**

- Detection accuracy

- Loss trends

- Model convergence

- Client-level performance

## 3. Repository Structure

```
Concept_drift_detection_adaptation/
│
├── Adaptation/              # Adaptation strategy experiments
├── Final/                   # Final experiment versions for thesis work
├── Loss Method Eval/        # Loss-based detection evaluation
├── Other Experiments/       # Additional experiments from the thesis work
├── Plots/                   # Generated plots and results
├── archive/                 # Older versions
│
├── thesis presentation.pdf  # thesis presentation
├── 
├── readme.txt               # Basic repo description
└── LICENSE

```

The repository consists mainly of Jupyter notebooks implementing experiments and evaluations.




## 4. System Architecture

Federated Learning Setup(FedAvg)

- Multiple clients train CNN models locally

- A global model is aggregated

- Each client may experience drift

- Server detects drift and adapts models

Workflow

- Initialize global CNN model

- Distribute to clients

- Clients train locally

- Simulate drift

- Detect drift

- Adapt model

- Aggregate models

- Evaluate performance


## 5. Drift Types Implemented
Sudden Drift

- Abrupt change in data distribution
-- method: label swap 

Gradual Drift

- Slow distribution shift across epochs
-- method: image augmentation over time

Hybrid Drift

- Combination of sudden and gradual changes

## 6. Detection Methods

The repository includes loss-based detection methods.

Typical logic:

- Monitor client loss

- Compare with moving averages

- Detect spikes or sustained increases

- Flag drifted clients

Detection can run:

- Server-side

- Per-client


## 7. Adaptation Strategies

After detecting drift:

- Train separate global models based detected drift

- Adjust learning rates

- Use optimized aggregation

Goal: restore performance for drifted clients without hurting others.


## 8. Experiments

Experiments include:

- Detection performance comparison

- Adaptation vs no adaptation

- Global vs client-specific models

- Different drift scenarios

## Metrics used:

- Loss

- Accuracy

- Detection precision

- Recall

- F1 score


## 9. Installation & Setup
Requirements

Python 3.8+

Common libraries:

```
torch
numpy
matplotlib
pandas
scikit-learn
jupyter
```

Run notebooks inside folders like:
```
Adaptation/

Loss Method Eval/

Final/
```

## 10. How to Use

Run baseline experiment

Open a notebook in 

```
Adatation/ 
```
and run all cells.

archive contains result logs and 
```
Plots/
```
folder contain scripts to generate plots

## 11. Outputs

The repo generates:

- Training loss plots

- Detection accuracy graphs

- Client performance comparisons

- Drift detection logs 
