# ECE-C147A-EMG

Refer to the gru or gru_cnn branches for instructions on how to run.

To change sampling rate, check `emg2qwerty/config/transforms/log_spectrogram.yaml` and edit `hop_length` under `logspec`.

`log.err` and `log.out` can be found under `emg2qwerty/logs` under  `submitit_logs` for every directory which ends in `_test`.