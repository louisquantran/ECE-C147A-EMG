# ECE-C147A-EMG

## Initial Setup

1. Download the data for the single user and make sure the data for the single user is stored at: ```ECE-C147A-EMG/emg2qwerty/data/```

2. Activate conda

```bash
conda activate emg2qwerty
```

3. As we experimented everything on 50 epochs, the baseline (default) performance can be tested by running:

```bash
python -m emg2qwerty.train --multirun \
  user=single_user \
  trainer.devices=1 \
  trainer.accelerator=gpu \
  trainer.max_epochs=50
```

## LSTM Architecture

## CNN Architecture

## TCN Architecture

Switch to the TCN branch where there will be further instructions in the README of that branch.

```bash
git checkout feature/standard-tcn
```

## GRU, CNN + GRU, TDSGRU Architectures

## Data Preprocessing and Augmentation

## Channel Ablation

## Data Ablation

Switch to the Data Ablation branch where there will be further instructions in the README of that branch.

```bash
git checkout data_ablation
```

## Sampling Rate
