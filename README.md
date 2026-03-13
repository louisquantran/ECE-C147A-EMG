# ECE-C147A-EMG (GRU, GRU+CNN hybrid, TDSGRU Model Experiments)

This repository contains our portion of the UCLA ECE C147A final project based on the **emg2qwerty** task: decoding QWERTY typing from surface EMG (sEMG) signals.

## Scope of This Repository

This is **not** the full group project repository. This repo only contains our experiments on comparing three architectures in the single-subject emg2qwerty setting:

- **GRU**
- **CNN + GRU hybrid**
- **TDSGRU**

Other project directions and different architectures were explored separately in other teammates’ work and are not the focus of this repository.

## Objective

The goal of this part of the project is to compare several recurrent and hybrid architectures and study how they affect **character error rate (CER)** on the provided single-subject split.

In particular, this repository investigates:

- whether a plain **GRU** can effectively model EMG typing sequences
- whether adding convolutional feature extraction before recurrence in a **CNN + GRU** hybrid improves performance
- whether a **TDSGRU** hybrid, which combines GRU-based temporal modeling with TDS-style refinement, can outperform the other two

## Models Included

### 1. GRU
A recurrent model that uses gated recurrent units to model temporal dependencies across the EMG sequence.

### 2. CNN + GRU Hybrid
A hybrid architecture that combines convolutional layers for local temporal feature extraction with a GRU for sequence modeling.

### 3. TDSGRU
A stronger hybrid architecture that combines a GRU-based recurrent encoder with a TDS-style fully connected refinement block before classification.

## Implementation Locations

The implementations for these models can be found in:

- `/emg2qwerty/config/model/*.yaml` - model configuration files and hyperparameters
- `/emg2qwerty/lightning.py` - PyTorch Lightning model definitions and training logic
- `/emg2qwerty/modules.py` - architecture components and encoder modules
