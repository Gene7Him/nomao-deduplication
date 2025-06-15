# Nomao Dataset Deduplication

## Overview
This project aims to predict whether two records refer to the same place using the Nomao dataset. By analyzing various attributes, I identify key features that influence the deduplication decision.

## Dataset
- **Source:** UCI Machine Learning Repository  
- **Instances:** 34,465 records  
- **Features:** 120 attributes (89 continuous, 31 nominal)  
- **Target:** Binary classification — duplicate (`1`) or not (`0`)  
- **Challenge:** Real-world noise, many missing values, and imbalanced labels


## Project Structure
- `data/`: Contains the dataset files.
- `notebooks/`: Jupyter notebooks for data analysis and modeling.
- `README.md`: Project documentation.
- `requirements.txt`: List of required Python packages.

## How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/Gene7Him/nomao-deduplication.git
   cd nomao-deduplication
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook notebooks/nomao_deduplication.ipynb
   ```

 ## Key Steps & Techniques

   # Preprocessing

        Mean imputation for missing values

        Scaling continuous features

        Label rounding (handling fuzzy floats like 0.999999999999)

        Label binarization for classification (1.0 vs others)

   # Visualization

        PCA scatter plot of training data

        Label distribution check

        SHAP summary plot (explainability)

   # Models

        LogisticRegression with class weights and saga solver

        RandomForestClassifier with parallel jobs

        Rule-based baseline using feature string matches (e.g., phone & address simulation)

   # Evaluation

        Accuracy, Precision, Recall, F1-score

        Confusion matrix analysis

        Label-wise support breakdown

## Rule-Based Baseline

I implemented a heuristic model that predicts a match when simulated "phone" and "address" fields are exactly equal. This provided a baseline to compare against ML models.

## Feature Importance

    Used Random Forest feature importances and SHAP values

    Identified key contributors to deduplication, simulating real-world attributes like name, address, and phone similarity

## 📈 Results Summary

| Model               | Accuracy | F1 Score | Precision | Recall |
|--------------------|----------|----------|-----------|--------|
| Logistic Regression|   0.59   |   0.52   |   0.47    |  0.59  |
| Random Forest      |   0.59   |   0.52   |   0.47    |  0.59  |
| Rule-Based Model   |   0.43   |   0.26   |   0.33    |  0.21  |

> Note: All models were trained on a subset of ~2000 records to reduce compute time. The full dataset contains over 30,000 samples and is highly imbalanced and noisy.

## Future Work

    Train on full dataset (currently subset used for performance)

    Add Levenshtein or fuzzy matching features for text columns

    Try advanced models like XGBoost or LightGBM

    Perform hyperparameter tuning with cross-validation

    Use active learning for improved sample efficiency    