# ECE-C147A-EMG

## Initial Setup

1. Download the data for the single user and make sure the data for the single user is stored at: ```ECE-C147A-EMG/emg2qwerty/data/```

2. Activate conda

```bash
conda activate emg2qwerty
```

3. As we experimented everything on 50 epochs, every architecture was trained by running:

```bash
python -m emg2qwerty.train --multirun model=<yaml file> user=single_user trainer.accelerator=gpu trainer.devices=1 trainer.max_epochs=50
```
For `<yaml file>`, look into `/emg2qwerty/config/model/*.yaml`, chose one, remove `.yaml`, and replace `<yaml file>` with the removed file name.

4. To obtain the test CER, the following command was used:
```bash
python -m emg2qwerty.train model=<yaml file> user=single_user 'checkpoint="<checkpoint path>"' train=False trainer.accelerator=gpu trainer.devices=1
```
For `<checkpoint path>`, each training will produce a log folder, containing the checkpoint and the detailed logs. Use the full file path for the best checkpoint.

## LSTM Architecture

Switch to the LSTM branch where there will be further instructions in the README of that branch.

```bash
git checkout lstm
```

## CNN Architecture

Switch to the CNN branch where there will be further instructions in the README of that branch.

```bash
git checkout feature/cnn
```

## TCN Architecture

Switch to the TCN branch where there will be further instructions in the README of that branch.

```bash
git checkout feature/standard-tcn
```

## GRU, CNN + GRU Hybrid, TDSGRU Architectures

Switch to the GRU, CNN + GRU Hybrid, TDSGRU branch where there will be further instructions in the README of that branch.

```bash
git checkout gru_cnn
```

## Data Preprocessing and Augmentation

Switch to the data preprocessing and augmentation branch where there will be further instructions in the README of that branch.

```bash
git checkout prepro_augment
```

## Channel Ablation

Switch to the channel ablation branch where there will be further instructions in the README of that branch.

```bash
git checkout channel_ablation
```

## Data Ablation

Switch to the data ablation branch where there will be further instructions in the README of that branch.

```bash
git checkout data_ablation
```

## Sampling Rate

Switch to the sampling rate branch where there will be further instructions in the README of that branch.

```bash
git checkout downsampling
```
