# Cradle — Baby Cry Classification Using Machine Learning

## Overview
This repository contains the ML component of a smart baby-monitoring cradle project. It demonstrates audio preprocessing, MFCC feature extraction, Random Forest classification, model evaluation, and prediction on a new recording.

## Cry categories
- Hungry
- Burping
- Discomfort
- Belly pain
- Tired

## Workflow
1. Load labeled audio recordings from class-specific folders.
2. Extract 13 MFCC coefficients from the first two seconds of each recording and average them over time.
3. Split data into training and held-out test sets.
4. Apply SMOTE only to training data when possible.
5. Train a Random Forest Classifier.
6. Evaluate with held-out accuracy, confusion matrix, precision, recall, and F1-score.
7. Visualize feature distributions and a spectrogram.
8. Test a new recording.

## Files
- `baby_cry_classification.ipynb` — cleaned end-to-end notebook.
- `requirements.txt` — main Python dependencies.
- `results/` — optional exported graphs from your own notebook run.

## Dataset setup
The notebook initially uses this Kaggle path:
`/kaggle/input/datasets/rajeshwarimurugadass/samples/donateacry_corpus`

The dataset should have one folder per class: `hungry`, `burping`, `discomfort`, `belly_pain`, and `tired`. Update `dataset_path` if your environment uses another path. Do not upload audio files unless you have permission to redistribute the dataset.

## Run
Install dependencies from `requirements.txt`, open the notebook, update `dataset_path`, and run the cells from top to bottom. For the final testing cell, update `new_audio` to the exact path of your test recording.

## Results
Run the notebook to calculate the held-out test accuracy and class-wise metrics. Earlier exploratory runs reported around 95% accuracy, but those figures should not be treated as validated if SMOTE was applied before the train/test split. This cleaned notebook splits first and applies SMOTE only to training data, so the reported score may be different.

## Limitations and responsible use
This is an experimental educational project. Baby-cry categories can overlap and labels may be imperfect. A prediction is not a medical diagnosis and should not replace caregiver judgment or professional advice.
