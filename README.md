# Multivariate Time Series Transformer Framework

This code corresponds to the [paper](https://dl.acm.org/doi/10.1145/3447548.3467401): George Zerveas et al. **A Transformer-based Framework for Multivariate Time Series Representtion Learning**, in _Proceedings of the 27th ACM SIGKDD Conference on Knowledge Discovery and Data Mining (KDD '21), August 14-18, 2021_.
ArXiV version: https://arxiv.org/abs/2010.02803

## Setup

1. Clone the repo by using HTTPS or either SSH, `git clone -b transformers.ts.dev https://github.com/htrivino20/mvts_transformer.git`
2. `cd mvts_transformer/`
3. Inside an already *existing* root directory, each experiment will create a time-stamped output directory, which contains model checkpoints, performance metrics per epoch, predictions per sample, the experiment configuration, log files etc. The following commands assume that you have created a new root directory inside the project directory like this: `mkdir experiments`
4. [We recommend creating and activating a `conda` or other Python virtual environment (e.g. `virtualenv`) to install packages and avoid conficting package requirements; otherwise, to run `pip`, the flag `--user` or `sudo` privileges will be necessary.] `pip install -r requirements.txt`
5. To see all command options with explanations, run: `python src/main.py --help`

## Train models from scratch
### Classification
```bash
python src/main.py --output_dir experiments --comment "classification from Scratch" --name WindTurbinesSensors_TRAIN.ts --records_file Classification_records.xls --data_dir ./WindTurbinesSensors/ --data_class tsra --pattern TRAIN --val_pattern TEST --epochs 10 --lr 0.001 --optimizer RAdam  --pos_encoding learnable  --task classification  --key_metric accuracy
```
