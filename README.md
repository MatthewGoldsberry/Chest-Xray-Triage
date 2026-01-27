# Chest X-Ray Triage Service

## Overview
This project implements a **deep learning–based chest X-ray triage system** designed to flag images that appear **abnormal** for prioritized human review.  
The system is intended as a **clinical decision support prototype**, not a diagnostic tool.

The project emphasizes **ML engineering best practices**, including reproducible training, model evaluation, and deployment as a containerized inference service.

---

## Problem Statement
Chest X-rays are one of the most commonly used medical imaging modalities. In high-volume settings, rapid identification of potentially abnormal images can help prioritize radiologist review.

This project frames the task as **binary triage**:
- **Normal**: No findings reported
- **Abnormal**: One or more findings reported

---

## Dataset
The model is trained using a subset of the **CheXpert** dataset released by Stanford University.

- Images: Frontal chest X-rays
- Labels:
  - `No Finding` → Normal
  - Any pathology label → Abnormal
- Uncertain labels are excluded

**Note:** This dataset is used strictly for research and educational purposes.

---

## Modeling Approach
- Pretrained convolutional neural networks (CNNs)
- Fine-tuning on medical imaging data
- Comparison of accuracy–latency tradeoffs across architectures

Primary evaluation metric:
- AUROC

Secondary metrics:
- Precision
- Recall

---

## Inference Service
The trained model is deployed as a **FastAPI service** that accepts an image and returns:
- Abnormality flag
- Confidence score
- Model version
- Inference latency

---

## Reproducibility
- Script-based training (no notebook dependency)
- Config-driven experiments
- Dockerized inference for consistent deployment

---

## Ethical Considerations
This system is a **research prototype** intended to demonstrate ML engineering techniques.  
It is **not** a diagnostic device and should not be used for clinical decision-making.

---

## Future Work
- Expanded benchmarking
- Model monitoring considerations
- Dataset shift analysis
