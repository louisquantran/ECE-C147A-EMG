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

To reproduce the TCN architecture experiments:

1. Switch to the TCN branch:

```bash
git checkout feature/standard-tcn
```

2. Run the training command:

```bash
python -m emg2qwerty.train --multirun \
  user=single_user \
  model=tcn \
  trainer.devices=1 \
  trainer.accelerator=gpu \
  trainer.max_epochs=50
```

3. log.out and some log.err have been committed to the repo and they will be found at: ```results-philemon/```

## GRU, CNN + GRU, TDSGRU Architectures

## Data Preprocessing and Augmentation

## Channel Ablation

## Data Ablation

To reproduce the data ablation experiments:

1. Make sure you are in the right branch:

```bash
git checkout gru_cnn
```

2. Example command for running the GRU model with a subset of 4 sessions:

```bash
python -m emg2qwerty.train --multirun \
  model=gru_ctc \
  user=single_user \
  +ablation=4_sessions \
  trainer.devices=1 \
  trainer.accelerator=gpu \
  trainer.max_epochs=50
```

   Replace the number 4 with 8 or 12 to test the model with a subset of 8/12 sessions.

3. To run the GRU model with the default (all sessions) just run the default training command with no ```+ablation=...``` parameter

log.out for each run are stored in: ```gru_data_ablations/```

## Sampling Rate
