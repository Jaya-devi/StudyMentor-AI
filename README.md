# StudyMentor AI — Student Performance Prediction & LLM Insights

StudyMentor AI is an end-to-end Machine Learning and Large Language Model (LLM) project developed as part of an AI and Machine Learning capstone.

The project analyzes student academic performance using the **UCI Student Performance dataset**, builds machine learning models to predict academic outcomes, and integrates an LLM to generate clear explanations for model predictions.

## Project Overview

| | |
|---|---|
| **Language** | Python |
| **Dataset** | UCI Student Performance Dataset |
| **ML Framework** | Scikit-learn |
| **LLM** | OpenRouter API |
| **Models** | Linear Regression, Logistic Regression, Decision Tree, Random Forest, Gradient Boosting |
| **API** | FastAPI |
| **Environment** | Jupyter Notebook, VS Code |

## Objectives

- Clean and analyze real-world educational data.
- Perform exploratory data analysis and feature engineering.
- Build and compare regression and classification models.
- Apply cross-validation and hyperparameter tuning.
- Evaluate models using appropriate performance metrics.
- Save and reload the best-performing model.
- Integrate an LLM for prediction explanations.
- Validate structured LLM responses and apply basic PII safety checks.

## Dataset

**UCI Student Performance Dataset — Portuguese Language**

The dataset contains **649 student records** with demographic, family, social, and academic attributes collected from secondary school students in Portugal.

Source: [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/320/student+performance)

The Portuguese dataset (`student-por.csv`) was selected because it contains more records than the corresponding Mathematics dataset.

## Machine Learning Workflow

```text
Raw Dataset
     ↓
Data Cleaning & Validation
     ↓
Exploratory Data Analysis
     ↓
Feature Engineering
     ↓
Encoding & Scaling
     ↓
Train / Test Split
     ↓
Model Training
     ↓
Cross-Validation & Hyperparameter Tuning
     ↓
Model Evaluation
     ↓
Best Model Selection
     ↓
Prediction API
     ↓
LLM-Based Explanation
```

## 1. Data Preparation & EDA

The first stage focuses on understanding and preparing the dataset.

Key activities:

- Missing-value analysis
- Duplicate detection
- Data-type validation
- Descriptive statistics
- Skewness analysis
- Outlier detection using IQR
- Correlation analysis
- Data visualization
- Feature exploration
- Data cleaning

Output:

`cleaned_data.csv`

## 2. Machine Learning

### Regression

- Linear Regression
- Ridge Regression

### Classification

- Logistic Regression
- Decision Tree
- Random Forest
- Gradient Boosting

### Techniques

- One-hot encoding
- Feature scaling
- Train-test split
- Cross-validation
- GridSearchCV
- Feature importance
- Feature ablation
- Learning curves
- Model serialization using Joblib

## 3. Model Evaluation

Models are evaluated using appropriate classification and regression metrics, including:

- Accuracy
- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion Matrix
- Cross-validation performance

The final model is selected based on comparative evaluation and cross-validation results.

### Model Performance

**Random Forest**

- Cross-validation AUC: **0.9785**
- Test AUC: **0.9436**

The tuned Random Forest demonstrated strong performance on the held-out test dataset.

## 4. LLM-Powered Prediction Explanation

The trained machine learning model is integrated with an LLM through the **OpenRouter API**.

The LLM receives structured prediction information and generates an easy-to-understand explanation of the result.

### LLM workflow

```text
Student Input
     ↓
Preprocessing
     ↓
ML Model
     ↓
Prediction + Probability
     ↓
Prompt Construction
     ↓
OpenRouter LLM
     ↓
Structured JSON Response
     ↓
Prediction Explanation
```

Implemented features:

- OpenRouter API integration
- Prompt engineering
- Structured JSON output
- JSON Schema validation
- Prediction explanation
- Temperature comparison
- PII detection
- Basic safety guardrails

## API

The project includes a **FastAPI-based inference layer** for serving model predictions.

Example workflow:

```text
Client Request
      ↓
FastAPI
      ↓
Preprocessing
      ↓
Trained ML Model
      ↓
Prediction
      ↓
LLM Explanation
      ↓
JSON Response
```

## Project Structure

```text
StudyMentor-AI/
│
├── part1/
│   ├── data/
│   ├── notebook/
│   ├── output/
│   └── plots/
│
├── part2/
│   ├── data/
│   ├── notebook/
│   ├── output/
│   └── plots/
│
├── part3/
│   ├── data/
│   ├── notebook/
│   ├── output/
│   └── plots/
│
├── part4/
│   ├── data/
│   ├── notebook/
│   └── output/
│
├── models/
├── requirements.txt
└── README.md
```

## Technologies

**Programming:** Python

**Data & ML:** Pandas, NumPy, Scikit-learn

**Visualization:** Matplotlib, Seaborn

**Model Management:** Joblib

**LLM Integration:** OpenRouter API, Requests

**Validation & Configuration:** JSON Schema, python-dotenv

**API:** FastAPI

**Development:** Jupyter Notebook, Visual Studio Code, Git/GitHub

## Key Learning Outcomes

This project demonstrates an end-to-end machine learning workflow covering:

- Data cleaning and EDA
- Feature engineering
- Regression and classification
- Ensemble learning
- Cross-validation
- Hyperparameter tuning
- Model evaluation
- Feature importance
- Model serialization
- API-based model inference
- LLM integration
- Prompt engineering
- Structured output validation
- Basic AI safety practices

## How to Run

### 1. Clone the repository

```bash
git clone <repository-url>
cd StudyMentor-AI
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure the API key

Create a `.env` file:

```text
OPENROUTER_API_KEY=your_api_key
```

### 4. Run the notebooks

Execute the notebooks in the following order:

```text
Part 1 → Part 2 → Part 3 → Part 4
```

Each stage uses outputs generated by the previous stage.

## Repository Contents

- Jupyter notebooks
- Cleaned dataset
- Trained model
- ML evaluation results
- Visualizations
- LLM integration
- FastAPI inference code
- Requirements file
- Project documentation
