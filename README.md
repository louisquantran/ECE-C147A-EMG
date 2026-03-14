# ECE-C147A-EMG

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