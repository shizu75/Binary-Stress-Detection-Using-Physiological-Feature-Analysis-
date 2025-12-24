# Binary Stress Detection Using Physiological Feature Analysis  
*A Research-Oriented Machine Learning Baseline*

---

## Overview
This repository presents a **implementation of binary stress classification** using statistical physiological features and classical machine learning techniques. The work is designed and structured as a **baseline experimental study**, suitable for inclusion in a **portfolio**, early-stage dissertation work, or comparative benchmarking in affective computing and biomedical signal analysis.

The primary objective is to **reliably distinguish stressed vs. unstressed physiological states** using interpretable models, rigorous preprocessing, and statistically sound evaluation protocols.

---

## Problem Statement
Physiological stress detection is a foundational problem in:
- Affective computing  
- Mental health monitoring  
- Human–computer interaction  
- Biomedical data analysis  

Rather than pursuing fine-grained emotion recognition, this work reframes the task as a **binary classification problem**, aligning with real-world applications where accurate stress detection is the primary concern.

---

## Dataset Description
The dataset consists of **numerical physiological features** recorded across multiple subjects and timestamps, annotated with emotional states.

### Label Engineering
Original emotional labels are consolidated as:
- **Stressed**
- **Unstressed** (merged from *neutral* and *relaxed*)

This consolidation:
- Reduces label noise
- Improves class separability
- Reflects realistic deployment objectives

### Feature Selection
The following non-predictive columns are removed:
- `timestamps` (temporal indexing)
- `Subject` (identity-related leakage)

This ensures the model learns **physiology-driven patterns**, not subject-specific artifacts.

---

## Exploratory Data Analysis (EDA)
- **Class distribution analysis** using histograms to assess imbalance  
- **Pearson correlation analysis** across physiological features  
- Diverging heatmap visualization to:
  - Identify multicollinearity
  - Highlight stress-sensitive feature relationships  

EDA is treated as a diagnostic tool, not merely visualization.

---

## Class Balancing Strategy
A **controlled subsampling approach** is employed:
- 250 stressed samples
- 250 unstressed samples (symmetrically sampled from early and late segments)

This avoids:
- Synthetic oversampling artifacts
- Distribution collapse
- Temporal bias

Such balancing is especially important in physiological datasets.

---

## Preprocessing Pipeline
- **Label Encoding** for binary target transformation  
- **Standardization (Z-score normalization)** across all features  

Standardization is critical due to the distance-based nature of the selected classifier.

---

## Model Architecture: K-Nearest Neighbors (KNN)
KNN is selected as a **transparent, non-parametric baseline** to:
- Establish interpretability
- Validate feature-space separability
- Provide a reference point for advanced models

### Configuration
- Neighbors: `k = 5`
- Distance metric: Euclidean (Minkowski, p = 2)
- Weighting: Uniform

This configuration represents a strong classical baseline without overfitting assumptions.

---

## Experimental Protocol
- Train/Test split: **70% / 30%**
- Fixed random seed for reproducibility
- Strict separation of evaluation data to prevent leakage

---

## Evaluation Metrics
The model is evaluated using both deterministic and probabilistic measures:

- **Accuracy** – overall performance
- **Confusion Matrix** – class-wise error analysis
- **Precision, Recall, F1-score** – robustness assessment
- **Log Loss** – confidence-aware probabilistic validation

Log loss evaluation elevates the study beyond simple classification accuracy.

---

## Key Results and Insights
- Demonstrates effective stress discrimination using classical ML
- Confirms discriminative value of physiological statistical features
- Provides an interpretable and reproducible baseline
- Establishes methodological grounding for:
  - SVMs
  - Ensemble methods
  - Deep learning and temporal models

---

## Research Significance
This repository is intended to serve as:
- A **baseline experiment** in a dissertation
- A **comparative benchmark** for advanced architectures
- A **methodological reference** for affective and biomedical ML studies

The emphasis is on **clarity, rigor, and reproducibility**, rather than performance inflation.

---

## Recommended Extensions
Future work can naturally extend this study by incorporating:
- Temporal modeling (LSTM, GRU, Transformers)
- Multimodal physiological fusion
- Feature selection via mutual information
- Model calibration and uncertainty estimation
- Cross-subject generalization studies

---

## Reproducibility
All preprocessing steps, sampling decisions, and evaluation procedures are explicitly defined to ensure full reproducibility and research transparency.

---

## Author Note
This repository is structured and documented to reflect **doctoral-level research standards**, prioritizing interpretability, experimental discipline, and scientific clarity.

---
