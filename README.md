# VSViG-Research-Reproduction
# VSViG: Real-Time Video Seizure Detection  
Research Reproduction in PyTorch

## Overview

This repository contains my reproduction of the research paper:

**"VSViG: Real-time Video based Seizure Detection via Skeleton-based Spatiotemporal ViG"**

The goal of the project was to reproduce the reported performance using the original architecture and evaluate training stability and preprocessing requirements.

---

## Dataset

- Raw video dataset (~26GB)
- Multiple patient recordings
- Skeleton-based pose representation used as input

The dataset is not included due to size and privacy constraints.

---

## My Contributions

- Implemented preprocessing pipeline for skeleton extraction and patch generation
- Reconstructed the VSViG architecture in PyTorch
- Built a full training workflow and experiment pipeline
- Trained the model for **200 epochs on NVIDIA A100 GPU**
- Achieved **5.99% error compared to 5.9% reported in the paper**

---

## Model Architecture

The VSViG model processes skeleton-based pose sequences using a spatiotemporal graph representation.

Pipeline:

```
Video → Pose Estimation → Skeleton Patches → VSViG Model → Seizure Probability
```

---

## Training

Example command:

```
python training/train.py
```

Training settings:

- Epochs: 200
- Optimizer: AdamW
- GPU: NVIDIA A100
- Framework: PyTorch

---

## Results

| Model | Error |
|------|------|
| Paper | 5.9% |
| Reproduction | 5.99% |

The results closely match the reported performance.

---

## Repository Structure

```
preprocessing/   data preparation
models/          VSViG architecture
training/        training scripts
evaluation/      evaluation scripts
notebooks/       experiments
```

---

## Future Work

- Improved preprocessing pipeline
- Multi-patient cross validation
- Optimized training speed
- Lightweight inference version
