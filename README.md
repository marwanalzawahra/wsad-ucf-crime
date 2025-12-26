# Weakly Supervised Video Anomaly Detection on UCF-Crime

This repository provides a **complete, leakage-safe, and reproducible pipeline** for  
**Weakly Supervised Video Anomaly Detection (WSVAD)** using the **UCF-Crime** dataset.

The implementation strictly follows **video-level evaluation**, avoiding common pitfalls such as frame-level leakage or invalid AUC computation.

---

## 📌 Key Features

- ✅ Video-level evaluation only (no frame-level metrics)
- ✅ Leakage-safe splits using `video_id` as groups
- ✅ Multiple Instance Learning (MIL)
  - Mean pooling (baseline)
  - Attention-based MIL
- ✅ Context-aware features (per-frame mean & std)
- ✅ Data augmentation applied to TRAIN only
- ✅ 5× repeated 70/30 splits with mean ± std reporting
- ✅ Automatic saving of CSV results, plots, and ZIP archives

---

## 🧠 Experimental Pipeline

1. Dataset preparation (UCF-Crime)
2. Frame extraction (fixed number per video)
3. Feature extraction (MobileNetV2 – ImageNet pretrained)
4. Bag construction (one bag per video)
5. Experiments:
   - Baseline (mean pooling)
   - Context-aware
   - Augmentation (train-only)
   - Context + Augmentation + MMD (diagnostic)
   - Attention-based MIL
6. Evaluation:
   - Accuracy
   - F1-score
   - ROC-AUC
   - Mean ± Std over 5 runs

---

## 📊 Experiments Included

| Experiment | Context | Augmentation | Attention |
|-----------|--------|--------------|-----------|
| baseline | ❌ | ❌ | ❌ |
| context | ✅ | ❌ | ❌ |
| aug | ❌ | ✅ (train only) | ❌ |
| context_aug_mmd | ✅ | ✅ (train only) | ❌ |
| attention_mil | ❌ | ❌ | ✅ |

---

## 🚨 Critical Evaluation Notes

- All metrics are computed at **VIDEO LEVEL**
- No frame-level ROC/AUC is reported
- No test-time augmentation
- No global statistics used for context features
- Explicit audits prevent train/test leakage

This design follows **correct WSVAD evaluation practice** and avoids common mistakes in prior literature.

---

## 🗂 Repository Structure

```text
wsad-ucf-crime/
 ├── wsad_ucf_crime_full_pipeline.ipynb
 ├── README.md
 ├── requirements.txt
 └── results/   (auto-generated)
