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

## Setup

```bash
conda create -n neuro-decode python=3.11
conda activate neuro-decode
pip install -r requirements.txt
```
## Data Source

The EEG data used in this project are obtained from the *EEG Motor Movement/Imagery Dataset* published by PhysioNet.

> Schalk, G. (2009). EEG Motor Movement/Imagery Dataset (Version 1.0.0). PhysioNet. DOI: 10.13026/C28G6P

Dataset URL: https://doi.org/10.13026/C28G6P

