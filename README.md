# ECE-C147A-EMG

## Data Ablation

To reproduce the data ablation experiments:

1. Make sure you are in the right branch:

```bash
git checkout data_ablation
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

4. log.out for each run are stored in: ```gru_data_ablations/```

## Files Created

The implementation for the data ablation can be found in:

- `/emg2qwerty/config/ablation/4_sessions.yaml` - Dataset of the first 4 sessions
- `/emg2qwerty/config/ablation/8_sessions.yaml` - Dataset of the first 8 sessions
- `/emg2qwerty/config/ablation/12_sessions.yaml` - Dataset of the first 12 sessions
