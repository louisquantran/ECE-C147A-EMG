# ECE-C147A-EMG

## Channel Ablation

To reproduce the channel ablation experiments:

1. Switch to the channel ablation branch:

```bash
git checkout channel_ablation
```

2. Example command for running the TDSGRU model with a channels per band of 12:

```bash
python -m emg2qwerty.train --multirun \
  user=single_user \
  model=gru_ctc \
  trainer.devices=1 \
  trainer.accelerator=gpu \
  trainer.max_epochs=50 \
  module.keep_channels_per_band=12
```

    Replace the number 12 with numbers like 2, 4, 8, 16 to test the model with other channels per band.

3. To run the TDSGRU model with the default number (16) of channels per band, just run the above command without the ```module.keep_channels_per_band``` parameter

4. log.out and some log.err have been committed to the repo and they will be found at: ```gru_channel_ablation/```

## Files Created/Changed

The implementations for the channel ablation can be found in:

- `/emg2qwerty/config/model/gru_ctc.yaml` - TDSGRU model configuration file and the added keep_channels_per_band hyperparameter
- `/emg2qwerty/lightning.py` - PyTorch Lightning model definitions and training logic