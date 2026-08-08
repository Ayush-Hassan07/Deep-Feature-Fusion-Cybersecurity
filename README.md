# Deep Feature Fusion for Cybersecurity

A research and development repository for Deep Feature Fusion techniques in cybersecurity applications, including zero-day detection, DDoS classification, malware analysis, and ensemble methods.

## Directory Structure

```
Deep-Feature-Fusion-Cybersecurity/
│
├── README.md
├── LICENSE
├── .gitignore
├── requirements.txt
│
├── data/
│   └── README.md
│
├── notebooks/
│   ├── single_dataset/
│   │   ├── zero_day/
│   │   ├── ddos/
│   │   └── malware/
│   │
│   ├── embedding_fusion/
│   │
│   └── ensemble/
│       ├── standard_4_class/
│       ├── adasyn/
│       └── adasyn_100k/
│
├── models/
│   ├── zero_day/
│   ├── ddos/
│   ├── malware/
│   └── ensemble/
│
├── embeddings/
│   ├── zero_day/
│   ├── ddos/
│   ├── malware/
│   └── fused/
│
└── results/
    ├── zero_day/
    ├── ddos/
    ├── malware/
    ├── ensemble/
    └── figures/
```

## Getting Started

1. Clone the repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Refer to `data/README.md` for dataset setup.
