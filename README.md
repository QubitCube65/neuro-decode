# neuro-decode

EEG-based motor imagery classification using machine learning.

This project decodes brain signals (EEG) to classify whether a person 
is imagining a left or right hand movement - a core problem in 
Brain-Computer Interface (BCI) research.

## What this project does

- Loads real EEG data from the PhysioNet EEGBCI dataset (109 subjects)
- Preprocesses raw signals with a bandpass filter (8–30 Hz)
- Segments continuous EEG into epochs around motor imagery events
- Extracts features from motor cortex channels (C3, Cz, C4)
- Trains a Linear Discriminant Analysis (LDA) classifier
- Evaluates with stratified 5-fold cross-validation (~70% accuracy)

## Notebooks

| Notebook | Description |
|---|---|
| `01_load_and_explore.ipynb` | Load and inspect raw EEG data |
| `02_preprocessing.ipynb` | Bandpass filtering and epoching |
| `03_classification.ipynb` | Feature extraction and LDA classification |

## Results

| Metric | Value |
|---|---|
| Classifier | Linear Discriminant Analysis |
| Features | Variance of C3, Cz, C4 channels |
| Cross-val accuracy | 70.0% ± 12.5% |
| Chance level | 50% |

## Setup

```bash
conda create -n neuro-decode python=3.11
conda activate neuro-decode
pip install -r requirements.txt
```

## Dataset

PhysioNet EEG Motor Movement/Imagery Dataset - automatically downloaded 
via MNE-Python on first run.
