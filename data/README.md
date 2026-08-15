# Datasets

The datasets used in this research are **not included in this repository** due to their size and to respect the distribution terms of the original dataset providers.

This project uses three cybersecurity datasets representing **DDoS, Zero-Day, and Malware attacks**.

## Datasets Used

| Dataset         | Threat Domain | Purpose                                                   |
| --------------- | ------------- | --------------------------------------------------------- |
| CIC-DDoS2019    | DDoS          | Training the CNN-LSTM-based DDoS feature extraction model |
| CIC-IDS2017     | Zero-Day      | Training the CNN-based Zero-Day feature extraction model  |
| CICMalDroid2020 | Malware       | Training the CNN-based malware feature extraction model   |

## Dataset Preparation

Each dataset is independently cleaned, encoded, normalized, and divided into:

* **60% Training**
* **20% Validation**
* **20% Testing**

The processed datasets are used to train task-specific deep learning models for feature extraction.

Each deep model generates a **128-dimensional embedding representation**. The embeddings generated from the DDoS, Zero-Day, and Malware datasets are subsequently aligned and concatenated to construct a unified **384-dimensional feature representation** for multi-attack classification.

## Expected Local Data

To reproduce the experiments, obtain the corresponding datasets from their original sources and prepare the required files locally.

The main dataset files used during development include:

```text
data/
├── CIC_IDS2017_400k_Multiclass.csv
├── final_merged_ddos_400k.csv
└── feature_vectors_syscallsbinders_frequency_5_Cat.csv
```

These files are intentionally excluded from the GitHub repository.

## Dataset Usage in the Pipeline

```text
CIC-DDoS2019
     │
     └──► CNN-LSTM
              │
              └──► 128D DDoS Embedding

CIC-IDS2017
     │
     └──► 1D-CNN
              │
              └──► 128D Zero-Day Embedding

CICMalDroid2020
     │
     └──► 1D-CNN
              │
              └──► 128D Malware Embedding

                       ↓

              Embedding Concatenation

                       ↓

              384D Fused Representation

                       ↓

         XGBoost / LightGBM / Random Forest

                       ↓

       Benign / DDoS / Zero-Day / Malware
```

## Important

The datasets remain subject to the terms and conditions established by their respective creators and distributors.

Users of this repository are responsible for obtaining the datasets from their original sources and complying with the applicable dataset licenses and usage requirements.

## Reference

For complete information about dataset preparation, preprocessing, feature extraction, embedding generation, and experimental methodology, please refer to the associated publication:

**Deep Feature Fusion with Ensemble Learning for Robust & Scalable Detection of DDoS, Zero-Day & Malware Attacks**

*2026 IEEE 2nd International Conference on Quantum Photonics, Artificial Intelligence, and Networking (QPAIN).*
