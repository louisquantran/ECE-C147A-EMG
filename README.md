# ECE-C147A-EMG

## CNN Architecture

To reproduce the CNN architecture experiments:

1. Switch to the CNN branch:

```bash
git checkout feature/cnn
```

2. Run the training command:

```bash
python -m emg2qwerty.train --multirun \
  user=single_user \
  model=cnn \
  trainer.devices=1 \
  trainer.accelerator=gpu \
  trainer.max_epochs=50
```

3. log.out and some log.err have been committed to the repo and they will be found at: ```results-chen/```

## Files Created/Changed

The implementations for the model can be found in:

- `/emg2qwerty/config/model/cnn.yaml` - CNN model configuration file and hyperparameters
- `/emg2qwerty/lightning.py` - PyTorch Lightning model definitions and training logic
- `/emg2qwerty/modules.py` - architecture components and encoder modules