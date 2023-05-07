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

In cell 4 of ECGPretraining.ipynb, change FAIRSEQ_SIG_DIR to where you installed fairseq-signals

```
FAIRSEQ_SIG_DIR = 'path/to/fairseq-signals'
```

# Download Data

In the directory where you want to store your data, run:

```bash
wget -r -N -c -np https://physionet.org/files/challenge-2021/1.0.3/
```

In cell 2 of ECGPretraining.ipynb, change PHYSIONET_PATH to the training file

In cell 2 of ECGPretraining.ipynb, change DATA_ROOT to where you want to keep processed data

```
PHYSIONET_PATH  = 'path/to/download/physionet.org/files/challenge-2021/1.0.3/training'
DATA_ROOT = 'path/to/processed'
```