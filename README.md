# Data Pulse — Generative Data Cleaning & Augmentation Tool

Data Pulse is an end-to-end pipeline for cleaning, preprocessing, and augmenting datasets using generative models. It combines **CTGAN** for large structured datasets and **GPT-Neo** for small or text-rich datasets, paired with a **React**-based dashboard for visualizing data quality and augmentation results.

## Overview

Real-world datasets are often small, imbalanced, or messy — which limits the performance of downstream machine learning models. Data Pulse addresses this by:
- Automatically cleaning and preprocessing raw data
- Generating high-quality synthetic data to augment small or imbalanced datasets
- Giving users a visual dashboard to inspect data quality before and after augmentation

## Key Results

- Achieved a **synthetic data quality score of 85–92%**, measured using [SDMetrics](https://docs.sdv.dev/sdmetrics/)
- Improved downstream ML model accuracy by **10–18%** after augmentation

## Features

- **Automated preprocessing module** — cleaning, normalization, outlier detection, and class-imbalance correction
- **Dual generative pipeline**:
  - CTGAN for large, structured tabular datasets
  - GPT-Neo for small or text-rich datasets
- **React dashboard** for:
  - Dataset preview
  - Distribution analysis
  - Statistical visualization
  - Augmentation reports

## Tech Stack

| Layer | Technology |
|---|---|
| Data processing | Python, Pandas |
| Synthetic data generation | CTGAN, GPT-Neo |
| Quality evaluation | SDMetrics |
| Frontend dashboard | React.js |

## Architecture

```
Raw Dataset
    │
    ▼
Preprocessing Module (cleaning, normalization,
outlier detection, class-imbalance correction)
    │
    ▼
   ┌────────────────────────┐
   │ Dataset type decision  │
   └────────────────────────┘
     │                    │
     ▼                    ▼
Large/structured      Small/text-rich
     │                    │
   CTGAN                GPT-Neo
     │                    │
     └─────────┬──────────┘
               ▼
      Synthetic Data Output
               │
               ▼
   Quality Evaluation (SDMetrics)
               │
               ▼
     React Dashboard (preview,
   distribution, augmentation report)
```

## Getting Started

> Fill in the exact commands once the repo is finalized — placeholders below follow the standard structure.

### Prerequisites
- Python 3.9+
- Node.js 16+
- pip, npm

### Installation

```bash
# Clone the repository
git clone https://github.com/vamshireddy05/data-pulse.git
cd data-pulse

# Backend setup
pip install -r requirements.txt

# Frontend setup
cd dashboard
npm install
```

### Usage

```bash
# Run the preprocessing + augmentation pipeline
python pipeline.py --input data/raw_dataset.csv --output data/augmented_dataset.csv

# Launch the dashboard
cd dashboard
npm start
```

## Project Structure

```
data-pulse/
├── data/                  # Sample raw & augmented datasets
├── preprocessing/         # Cleaning & normalization modules
├── models/                # CTGAN and GPT-Neo pipelines
├── evaluation/            # SDMetrics-based quality scoring
├── dashboard/              # React frontend
├── pipeline.py             # Main entry point
└── requirements.txt
```

## Future Scope

- Extend support to time-series and image datasets
- Add automated hyperparameter tuning for CTGAN/GPT-Neo
- Deploy as a hosted web service for non-technical users

## Author

**Vamshi Reddy P**
[LinkedIn](https://www.linkedin.com/in/vamshi-reddy-p-036360364) · [GitHub](https://github.com/vamshireddy05)
