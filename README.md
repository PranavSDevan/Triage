# Medical Triage Classification System

A machine learning-based system for classifying patient triage levels in emergency departments using the Korean Triage and Acuity Scale (KTAS).

## 📋 Overview

This project implements a Random Forest classifier to predict appropriate triage levels for patients based on their symptoms, vital signs, and other clinical indicators. The model helps healthcare professionals make faster and more accurate triage decisions in emergency settings.

## 🎯 Features

- **Automated Triage Classification**: Predicts KTAS levels (1-5) based on patient data
- **SMOTE Implementation**: Handles class imbalance in the training data
- **Multi-feature Analysis**: Processes both numerical and text data (chief complaints)
- **TF-IDF Vectorization**: Analyzes patient chief complaints using natural language processing
- **Comprehensive Preprocessing**: Handles missing values and data type conversions

## 📊 Dataset

The dataset contains 1267 patient records with 24 features including:
- Patient demographics (age, sex, group)
- Arrival information (mode, time)
- Vital signs (blood pressure, heart rate, respiratory rate, temperature, oxygen saturation)
- Clinical indicators (pain level, mental status, injury status)
- Chief complaints (text descriptions)
- KTAS expert ratings (target variable)

## 🚀 Getting Started

### Prerequisites

```bash
pip install -r requirements.txt
```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/Tahleel1611/Triage.git
cd Triage
```

2. Install dependencies:
```bash
pip install pandas scikit-learn imbalanced-learn numpy jupyter
```

3. Place your dataset file (`data.csv`) in the root directory

### Usage

Open and run the main Jupyter notebook:
```bash
jupyter notebook Triage.ipynb
```

## 📈 Model Performance

- **Accuracy**: 70%
- **Algorithm**: Random Forest Classifier with SMOTE
- **Features**: 15 numerical features + text features from chief complaints

### Classification Report:

| KTAS Level | Precision | Recall | F1-Score | Support |
|------------|-----------|--------|----------|----------|
| 1          | 1.00      | 1.00   | 1.00     | 6        |
| 2          | 0.76      | 0.71   | 0.74     | 49       |
| 3          | 0.67      | 0.75   | 0.70     | 91       |
| 4          | 0.69      | 0.78   | 0.73     | 83       |
| 5          | 0.67      | 0.16   | 0.26     | 25       |

## 🛠️ Technical Details

### Model Pipeline:
1. **Data Preprocessing**
   - Handle missing values using median imputation
   - Convert text to numerical format where needed
   - Text vectorization using TF-IDF

2. **Feature Engineering**
   - StandardScaler for numerical features
   - TfidfVectorizer for chief complaint text

3. **Class Balancing**
   - SMOTE (Synthetic Minority Over-sampling Technique)

4. **Classification**
   - Random Forest with optimized hyperparameters
   - Class weight balancing

### Hyperparameters:
- `n_estimators`: 100
- `max_depth`: None
- `min_samples_split`: 5
- `min_samples_leaf`: 1
- `class_weight`: 'balanced'

## 📁 Project Structure

```
Triage/
│
├── README.md                 # Project documentation
├── Triage.ipynb             # Main analysis notebook
├── data.csv                 # Dataset (not included)
├── requirements.txt         # Python dependencies
├── 76%.ipynb               # Additional experiments
├── Presentbest.ipynb       # Presentation notebook
└── .ipynb_checkpoints/     # Jupyter checkpoints
```

## 🔧 Future Improvements

- [ ] Improve accuracy for KTAS level 5 predictions
- [ ] Implement deep learning models for comparison
- [ ] Add real-time prediction API
- [ ] Create web-based interface for clinical use
- [ ] Expand dataset with more diverse cases
- [ ] Add explainability features (SHAP values)

## 📝 License

This project is open source and available under the MIT License.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

## 👥 Authors

- Original work by [PranavSDevan](https://github.com/PranavSDevan)
- Forked and improved by [Tahleel1611](https://github.com/Tahleel1611)

## 📚 References

- Korean Triage and Acuity Scale (KTAS)
- SMOTE: Synthetic Minority Over-sampling Technique
- Random Forest Classification

## ⚠️ Disclaimer

This tool is for research and educational purposes only. It should not be used as the sole basis for clinical decisions. Always consult with qualified healthcare professionals for patient care decisions.
