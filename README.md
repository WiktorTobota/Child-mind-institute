# Kaggle: Child Mind Institute - Problematic Internet Use

## Project Description
This repository contains my solution to a Kaggle competition. The goal of the competition is to predict the `sii` variable (Severity Impairment Index), which represents four levels of problematic internet use (0–3).

The training and test datasets contain various features describing individuals, such as age, gender, physical measurements, fitness test results, and internet usage habits. The challenge involves preprocessing the data, building and comparing classification models, and generating predictions for the test dataset.

## Approach

1. **Exploratory Data Analysis (EDA)**:
   - Displaying basic information and descriptive statistics about the dataset.
   - Analyzing and visualizing the distribution of the target variable (`sii`).
   - Identifying missing values in the dataset.

2. **Data Preprocessing**:
   - Filling missing values in numerical columns using the column mean, excluding the target variable.
   - Encoding categorical variables using `one-hot encoding`.
   - Removing rows with missing target values.
   - Aligning columns between the training and test datasets.
   - Standardizing numerical features using `StandardScaler`.

3. **Modeling**:
   - Comparing three classification models:
     - `XGBClassifier`
     - `RandomForestClassifier`
     - `LogisticRegression`
   - Evaluating models using 5-fold cross-validation.
   - Calculating accuracy, classification reports, and confusion matrices.
   - Automatically selecting the model with the highest average cross-validation accuracy.
   - Training the selected model on the full labeled training dataset.

4. **Results**:
   - `XGBClassifier` achieved an average cross-validation accuracy of **57.93%**.
   - `RandomForestClassifier` achieved an average cross-validation accuracy of **59.10%**.
   - `LogisticRegression` achieved the highest average cross-validation accuracy of **59.28%**.
   - Class `0` was the most accurately predicted class across all models.
   - Classes `2` and `3` were particularly difficult to classify.

5. **Evaluation and Submission**:
   - Evaluating models using cross-validation accuracy, precision, recall, and F1-score.
   - Analyzing confusion matrices to identify classification errors.
   - Selecting `LogisticRegression` as the best-performing model.
   - Generating predictions for the test dataset and saving them to a `results.csv` file.
