<div align="center">

# 👶 CRADLE
### *Intelligent Baby Cry Classification Using Machine Learning*

**Turning baby cries into meaningful audio classifications with Machine Learning.**

<br>

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Machine Learning](https://img.shields.io/badge/Machine%20Learning-8A2BE2?style=for-the-badge)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-F7931E?style=for-the-badge&logo=scikitlearn&logoColor=white)
![Librosa](https://img.shields.io/badge/Audio%20Processing-Librosa-008080?style=for-the-badge)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

</div>

---

## 🌟 About the Project

**Cradle** is a baby-monitoring project exploring how Machine Learning can help classify baby cries into different categories.

Babies communicate their needs through crying, but understanding the possible reason behind a cry can be challenging. Cradle's ML component analyzes audio recordings, extracts meaningful sound features, and predicts a category based on patterns learned from labeled audio data.

The broader project aims to bring together **audio-based Machine Learning, hardware simulation, and future camera-based monitoring** to explore smarter baby-monitoring solutions.

> 💡 **Our idea:** Use sound as data and Machine Learning to identify patterns in baby cries.

---

## 🎯 Project Goals

- 🎵 Analyze baby-cry audio recordings.
- 🧠 Extract meaningful audio features using MFCCs.
- 🌳 Train a Random Forest Classifier for multiclass prediction.
- 📊 Evaluate the model using classification metrics and visualizations.
- 🔔 Establish a foundation for future monitoring notifications and alerts.

---

## 🍼 Cry Categories

The model is designed to classify recordings into five dataset categories:

| Category | Label |
|---|---|
| 🍼 Hungry | `hungry` |
| 💨 Burping | `burping` |
| 🧸 Discomfort | `discomfort` |
| 🩺 Belly Pain | `belly_pain` |
| 😴 Tired | `tired` |

*These are dataset labels. A model prediction does not confirm a baby's actual need or medical condition.*

---

## ⚙️ How Cradle Works

```text
       🎙️ Baby-Cry Audio
               │
               ▼
       🎧 Audio Preprocessing
               │
               ▼
       📈 MFCC Feature Extraction
               │
               ▼
        🗂️ Dataset Preparation
               │
               ▼
       ⚖️ SMOTE (Training Data)
               │
               ▼
       🌳 Random Forest Classifier
               │
               ▼
       📊 Model Evaluation
               │
               ▼
       🍼 Predicted Cry Category
```

### 🔍 The Machine Learning Pipeline

**01 — Audio Processing 🎧**  
Audio recordings are loaded and prepared for feature extraction using Librosa.

**02 — Feature Extraction 📈**  
Mel-Frequency Cepstral Coefficients (MFCCs) represent important characteristics of the audio signal as numerical features.

**03 — Data Preparation 🗂️**  
The extracted features and labels are organized into training and testing datasets.

**04 — Class Balancing ⚖️**  
SMOTE can generate synthetic minority-class training examples to help address class imbalance. It is applied to training data, not the held-out test set.

**05 — Model Training 🌳**  
A Random Forest Classifier learns patterns from the extracted features to predict the audio category.

**06 — Evaluation 📊**  
The model is evaluated using accuracy, precision, recall, F1-score, and a confusion matrix.

**07 — New-Audio Prediction 🍼**  
A new audio recording can be processed using the same feature-extraction procedure and passed to the trained model for a prediction.

---

## 🧠 Why Random Forest?

Cradle uses the **Random Forest Classifier**, an ensemble learning algorithm that combines predictions from multiple decision trees.

Reasons for choosing it include:

- Supports multiclass classification.
- Can learn nonlinear relationships between audio features and labels.
- Combines multiple trees rather than relying on a single decision tree.
- Provides a practical baseline for experimenting with extracted audio features.

The model's actual performance must be established by running and evaluating the notebook.

---

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| 🐍 Python | Main programming language |
| 🎧 Librosa | Audio loading and feature extraction |
| 🔢 NumPy | Numerical operations |
| 🗃️ Pandas | Data organization and analysis |
| 📊 Matplotlib | Performance visualizations |
| 🤖 Scikit-learn | Model training and evaluation |
| ⚖️ Imbalanced-learn | SMOTE for training-data balancing |
| 📓 Kaggle Notebooks | Development and experimentation |
| 🐙 GitHub | Source code and project documentation |

---

## 📊 Model Evaluation

The notebook evaluates the classifier using:

| Metric | What It Tells Us |
|---|---|
| 🎯 Accuracy | Overall proportion of correct predictions |
| 🔎 Precision | How reliable predictions for a category are |
| 📥 Recall | How many actual samples of a category are identified |
| ⚖️ F1-score | Balance between precision and recall |
| 🧩 Confusion Matrix | Which categories are predicted correctly or confused with others |

**Note:** Evaluation values are produced by running the notebook. They should not be interpreted as verified results until the current version has been executed and tested.

---

## 🚀 Getting Started

### Option 1: Run on Kaggle

1. Open Kaggle Notebooks.
2. Create a notebook or open an existing one.
3. Add the baby-cry dataset to the notebook.
4. Open `baby_cry_classification.ipynb`.
5. Verify that the dataset paths match the attached dataset.
6. Run the cells in order.
7. Update the test-audio path before trying a new recording.

### Option 2: Run Locally

**Prerequisites:** Python and a compatible Jupyter environment.

**Step 1 — Get the project**

Download or clone this repository.

**Step 2 — Install dependencies**

```bash
pip install -r requirements.txt
```

**Step 3 — Open the notebook**

```bash
jupyter notebook
```

Open `baby_cry_classification.ipynb` in the browser.

**Step 4 — Configure your data**

The dataset is not included in this repository. Obtain it separately and update the dataset and test-audio paths for your environment.

**Step 5 — Run the notebook**

Execute the cells in order and inspect the evaluation results.

---

## 📁 Repository Structure

```text
Cradle-Baby-Cry-Classification-ML/
│
├── 📓 baby_cry_classification.ipynb
│   └── Audio processing, model training, evaluation
│
├── 📄 README.md
│   └── Project overview and setup instructions
│
├── 📦 requirements.txt
│   └── Required Python libraries
│
└── 🚫 .gitignore
    └── Files Git should ignore
```

---

## 🔮 Future Enhancements

- 📱 Develop an application for monitoring notifications.
- 🔔 Explore alerts based on model predictions.
- 📷 Investigate integration with a 360-degree camera for broader visual monitoring.
- ⚡ Explore real-time audio classification.
- 📈 Improve reliability using more diverse, representative audio data.
- 🔌 Integrate and test the ML component with the broader hardware system.

---

## ⚠️ Limitations and Responsible Use

- Model performance depends on dataset quality and diversity.
- Similar cries may be difficult to distinguish using audio features alone.
- Predictions are estimates based on learned patterns, not confirmed explanations of a baby's needs.
- This project is experimental and is not a medical diagnostic system.
- Real-time monitoring, camera integration, and automated alerts require separate implementation and validation.

---

## 💙 Project Vision

Cradle explores how audio processing and Machine Learning can contribute to a more informative baby-monitoring system.

By combining feature extraction, classification, and performance evaluation, this project provides a foundation for further experimentation with intelligent monitoring technologies.

<div align="center">

### 🌱 Learn. Build. Experiment. Improve.

**Cradle — Exploring smarter baby monitoring through Machine Learning.**

</div>
