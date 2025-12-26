# Weakly Supervised Video Anomaly Detection on UCF-Crime

This repository presents a research-oriented implementation of a **weakly supervised
video anomaly detection** framework based on **Multiple Instance Learning (MIL)**.
The approach relies exclusively on video-level labels and is evaluated on the
**UCF-Crime** benchmark dataset.

The primary focus of this work is on:
- Robust anomaly scoring under weak supervision
- Efficient temporal aggregation using MIL
- Practical suitability for real-time or near real-time scenarios

---

## Research Motivation
Video anomaly detection in surveillance environments is challenged by the high cost
and subjectivity of frame-level annotations. Weakly supervised learning provides a
scalable alternative by learning from coarse video-level labels while still enabling
meaningful anomaly localization.

---

## Method Overview
The proposed framework follows a standard MIL-based pipeline:
- Feature extraction from fixed-length video segments
- MIL-based aggregation of segment-level representations
- Video-level anomaly classification
- Generation of frame/segment-level anomaly scores for evaluation

---

## Dataset
All experiments are conducted on the **UCF-Crime dataset**.
Due to licensing and copyright restrictions, the dataset is **not included** in this
repository.

---

## Project Structure
```text
wsad-ucf-crime/
│
├── data/               # Dataset handling (not included)
├── features/           # Extracted visual features
├── models/             # MIL and classification models
├── experiments/        # Training and evaluation scripts
├── results/            # Quantitative results and metrics
├── figures/            # Visualizations and plots
└── README.md
