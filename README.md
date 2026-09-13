# Bone Fracture Detection Pipeline

## Overview
This repository contains an advanced medical AI pipeline for bone fracture detection using YOLOv10n with attention mechanisms and anti-overfitting techniques. The pipeline is designed to achieve high precision (>95%) in detecting 10 types of fractures from the HBFMID dataset.

## Features
- Modified YOLOv10n architecture with attention mechanisms (CBAM, SE, ECA blocks)
- Comprehensive regularization suite (DropBlock, Mixup, CutMix, Label Smoothing)
- Advanced optimization (AdamW, Cosine Annealing, Warmup)
- Medical-safe data augmentation
- Ensemble model averaging for robustness
- Clinical-grade evaluation and interpretability

## Dataset
The pipeline uses the HBFMID dataset containing 10 fracture types:
1. Comminuted
2. Greenstick
3. Healthy
4. Linear
5. Oblique Displaced
6. Oblique
7. Segmental
8. Spiral
9. Transverse Displaced
10. Transverse

## Installation
1. Clone this repository
2. Install required packages:
   ```
   pip install -r requirements.txt
   ```
3. Ensure you have the Bone-Best.pt model file in the repository root

## Usage
Run the provided Jupyter notebook:
```
jupyter notebook "Bone Model Notebook Final.ipynb"
```
Follow the notebook instructions to train, evaluate, and use the fracture detection model.

## Model Files
- Bone-Best.pt: Trained YOLOv10n model weights

## Overall Metrics

| Metric | Score |
|--------|-------|
| mAP@0.5 | 0.933 |
| mAP@0.5:0.95 | 0.521 |
| Overall Precision | 0.969 |
| Overall Recall | 0.900 |
| Overall F1 | 0.933 |
| Macro F1 | 0.926 |
| AUC-ROC (equivalent: mAP@0.5) | 0.933 |
| Training Time | ~2.5 hours (200 epochs on Kaggle T4 GPU) |
| Inference Time | 18.8 ms/image (GPU), 56.1 ms/image (CPU) |
| Model Size | 5.51 MB (.pt) / 5.40 MB (.pth) |
| Parameters | 2,267,118 |
| Speed Breakdown | 0.9ms preprocess, 18.8ms inference, 0.0ms loss, 0.2ms postprocess |

## License
See LICENSE file for usage restrictions.

## Disclaimer
This is a research prototype and not intended for clinical use without proper validation and regulatory approval.