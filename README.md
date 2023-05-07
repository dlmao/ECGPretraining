# Setup Environment

* [PyTorch](https://pytorch.org) version >= 1.5.0

```bash
pip install -r requirements.txt
```

* In a separate directory, install project fork of fairseq-signals (original code by authors [here](https://github.com/Jwoo5/fairseq-signals)):

```bash
git clone https://github.com/dlmao/fairseq-signals
cd fairseq-signals
pip install --editable ./
```

In ECGPretraining.ipynb, change FAIRSEQ_SIG_DIR to where you installed fairseq-signals

```
FAIRSEQ_SIG_DIR = 'path/to/fairseq-signals'
```

# Download Data

In the directory where you want to store your data, run:

```bash
wget -r -N -c -np https://physionet.org/files/challenge-2021/1.0.3/
wget -r -N -c -np https://physionet.org/files/nstdb/1.0.0/
```

In ECGPretraining.ipynb, PHYSIONET_PATH to the training file

In ECGPretraining.ipynb, DATA_ROOT to where you want to keep processed data

```
PHYSIONET_PATH  = 'path/to/download/physionet.org/files/challenge-2021/1.0.3/training'
DATA_ROOT = 'path/to/processed'
```

# Use a Pretrained Model

The two pre-trained models can accessed using 

Wave2vec 2.0 + CMSC + RLM is under the name "w2vcmscrlm.pt"

Wave2vec 2.0 + CMSC is under the name  "w2vcmsc.pt"

Simply replace PRETRAIN_CHECKPOINT with the location of your local Wave2vec 2.0 + CMSC + RLM and PRETRAIN_CHECKPOINT_CMSC with Wave2vec 2.0 + CMSC.

# Running Traditional Classification

Both RESNET and custom CNN use the same trainer and validator. To run one, just set model to the corresponding model to be run.
