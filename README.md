# ECE-C147A-EMG (TDSGRU Preprocessing and Augmentation Experiments)

This repository contains our portion of the UCLA ECE C147A final project based on the **emg2qwerty** task: decoding QWERTY typing from surface EMG (sEMG) signals.

## Scope of This Repository

This is **not** the full group project repository. This branch specifically contains our experiments using **TDSGRU** to study the effect of **data preprocessing** and **data augmentation** on EMG-to-text decoding performance in the **single-subject emg2qwerty setting**.

Rather than comparing different model families, this part of the project keeps the architecture fixed and focuses on changing the input pipeline to evaluate whether preprocessing and augmentation can improve generalization and reduce **character error rate (CER)**.

## Objective

The goal of this branch is to investigate how different preprocessing and augmentation methods affect the performance of a **TDSGRU-based** model.

In particular, we study:

- whether **standardization** improves training stability and performance
- whether **Gaussian noise augmentation** improves robustness to signal variation
- whether combining **standardization + Gaussian noise** gives further improvement
- whether **magnitude clipping** helps suppress outliers in the EMG signal

By keeping the model architecture the same across all experiments, we can attribute performance differences more directly to the data pipeline rather than to changes in the network itself.

## Model

All experiments in this branch use **TDSGRU** as the sequence model.

TDSGRU was chosen because it provides the best overall performance in both validation CER and test CER.

## Experiment Variants

This branch includes the following TDSGRU experiment settings:

### 1. `tdsgru_standardize`
Applies **standardization** to the input EMG features before training.

Purpose:
- normalize feature scale
- reduce variation across channels
- improve optimization stability

### 2. `tdsgru_gaussian`
Applies **Gaussian-noise augmentation** during training.

Purpose:
- improve robustness to noisy EMG signals
- reduce overfitting
- simulate small signal perturbations during training

### 3. `tdsgru_gaussian_standardize`
Combines **standardization** with **Gaussian-noise augmentation**.

Purpose:
- test whether normalization and augmentation work well together
- evaluate whether the combination improves CER more than either method alone

### 4. `tdsgru_clip_magnitude`
Applies **magnitude clipping** to the EMG input.

Purpose:
- suppress extreme signal values
- reduce the influence of outliers
- stabilize the input distribution seen by the model

## Implementation

The preprocessing and augmentation implementations used in this branch can be found at:

- `/emg2qwerty/transforms.py`
- `/emg2qwerty/config/transforms/log_spectrogram.yaml`

These files contain the transform definitions and configuration settings used to apply the preprocessing and augmentation pipelines in the experiments.

## Best Result

Among the preprocessing and augmentation variants explored in this branch, **TDSGRU + Standardize** achieved the best overall performance.

- **Best Validation CER:** **16.64**
- **Best Test CER:** **16.71**

This result suggests that simple input standardization was more effective than the other augmentation and preprocessing methods tested in this branch for improving TDSGRU decoding performance.
