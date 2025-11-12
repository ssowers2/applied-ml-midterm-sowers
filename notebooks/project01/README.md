# 🍄 Mushroom Classification Analysis  
**Author:** Sabriya Sowers  
**Date:** November 10, 2025  

## Project Overview  
This project applies **machine learning classification techniques** to predict whether a mushroom is **edible or poisonous** based on its physical characteristics.  
The dataset used is the **UCI Mushroom Dataset**, containing **8,124 records and 23 categorical features** that describe observable mushroom traits such as color, odor, cap shape, and gill size.  

The goal of this project was to explore, clean, and model this data to identify patterns that distinguish edible from poisonous mushrooms.

---

## Dataset Details  
- **Source:** UCI Machine Learning Repository  
- **Instances:** 8,124  
- **Features:** 23 categorical (including target `class`)  
- **Target Variable:**  
  - `class` → 0 = edible, 1 = poisonous  
- **Missing Values:** Present only in `stalk_root` (filled with mode)

---

## Data Preparation  
1. Loaded and inspected the dataset for missing values and structure.  
2. Renamed columns for clarity.  
3. Imputed missing values in `stalk_root` using the mode.  
4. Converted all categorical features to numeric form using one-hot encoding.  
5. Split the dataset into training and testing sets (80/20).  

---

## Exploratory Data Analysis  
- Count plots were created for key features (`odor`, `spore_print_color`, etc.) to visualize category distributions.  
- Patterns showed that specific odors and spore colors were strong indicators of toxicity.  
- The dataset was well balanced (approximately 52% edible vs. 48% poisonous).  

---

## Modeling and Evaluation  
Two classification models were implemented and compared:

| Model | Accuracy | Key Notes |
|-------|-----------|-----------|
| **Decision Tree** | 100% | Accurately classified all records; highly interpretable |
| **Random Forest** | 100% | More robust and stable; confirms strong feature separability |

**Evaluation Metrics:**  
- Accuracy  
- Precision  
- Recall  
- F1-Score  
- Confusion Matrix Visualization  

---

## Key Findings  
- Features such as `odor`, `gill_size`, and `spore_print_color` are strong predictors of edibility.  
- Both models achieved perfect accuracy, reflecting the dataset’s high separability.  
- Random Forest provides better generalization potential despite identical accuracy results.  

---

## Tools and Libraries  
- Python  
- pandas, numpy  
- matplotlib, seaborn  
- scikit-learn (DecisionTreeClassifier, RandomForestClassifier, metrics)

---

## Reflections  
- **Challenges:** Managing a fully categorical dataset required careful encoding and verification.  
- **Insights:** The mushroom dataset strongly demonstrates how feature relationships drive predictive performance.  
- **Next Steps:**  
  - Experiment with additional models such as Logistic Regression or SVM.  
  - Perform feature importance analysis for interpretability.  
  - Validate with cross-validation or external data to assess overfitting.

---

## Conclusion  
This project demonstrates the complete data science process — from loading and cleaning data, to feature engineering, modeling, and evaluation.  
The models’ perfect accuracy illustrates clear relationships between physical traits and mushroom edibility, while also highlighting the importance of validating model generalization beyond one dataset.


### Model Summary

| Model Type            | Features Used            | Accuracy | Precision | Recall | F1-Score | Notes |
|----------------------|--------------------------|:-------:|:--------:|:-----:|:-------:|-------|
| Decision Tree        | All encoded features     | 1.00    | 1.00     | 1.00  | 1.00    | 80/20 stratified split; perfectly separates classes |
| Random Forest (100)  | All encoded features     | 1.00    | 1.00     | 1.00  | 1.00    | Ensemble confirmation of perfect separation; more robust to variance |


### Setup virtual environment
1. uv venv
2. uv python pin 3.12
3. uv sync --extra dev --extra docs --upgrade
4. .\.venv\Scripts\Activate
5. uv add --dev pre-commit ruff
6. uv run python --version