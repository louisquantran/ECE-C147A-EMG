# ECE-C147A-EMG

## LSTM Architecture

To reproduce the TCN architecture experiments:

1. Switch to the TCN branch:

```bash
git checkout lstm
```

2. Run the training command:

```bash
python -m emg2qwerty.train --multirun \
  user=single_user \
  model=tds_lstm_ctc \
  trainer.devices=1 \
  trainer.accelerator=gpu \
  trainer.max_epochs=50
```

(There are also  `tds_lstm_no_mlp` and `tds_lstm_conv_ctc` as model choices.)

3. log.out and some log.err have been committed to the repo and they will be found at: ```./logs/```. Log.err and log.out will be found under ```submitit_logs``` under each directory. Directories ending with `results` are for testing and all others are for training.

## Files Created/Changed

The implementations for the model can be found in:

- `/emg2qwerty/config/model/tds_lstm_no_mlp.yaml`
- `/emg2qwerty/config/model/tds_lstm_conv_ctc.yaml`
- `/emg2qwerty/config/model/tds_lstm_ctc.yaml`
- `/emg2qwerty/lightning.py` - PyTorch Lightning model definitions and training logic
- `/emg2qwerty/modules.py` - architecture components and encoder modules