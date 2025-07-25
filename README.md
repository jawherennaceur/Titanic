# Titanic Survival Prediction

This project uses machine learning to predict passenger survival on the Titanic based on features like age, class, sex, fare, family size, and more. The model is trained on the Titanic dataset from [Kaggle](https://www.kaggle.com/competitions/titanic/data).

## Overview

- Data source: `train.csv` and `test.csv`
- Goal: Predict whether a passenger survived or not
- Model used: Logistic Regression
- Output: `submission.csv` containing predictions for the test set

## Project Structure

- `train.csv`: Training data
- `test.csv`: Test data
- `submission.csv`: Prediction results for Kaggle submission
- `main.py` (or equivalent): All preprocessing, feature engineering, modeling, and evaluation steps

## Steps

### 1. Data Exploration

- Checked for missing values, duplicates, and data types
- Explored distributions of key features using bar charts and KDE plots

### 2. Feature Engineering

- Extracted `Title` from `Name` and encoded it
- Created `FamilySize` from `SibSp` and `Parch`
- Converted `Cabin` to its first letter
- Dropped irrelevant columns: `PassengerId`, `Name`, `SibSp`, `Parch`

### 3. Encoding

- Used `LabelEncoder` for `Sex`, `Ticket`, and `Title`
- Mapped `Cabin` and `Embarked` manually to numeric values

### 4. Handling Missing Values

- Filled missing `Age` using median age by `Title`
- Filled missing `Fare` using median fare by `Pclass`
- Filled missing `Cabin` using median cabin value by `Pclass`
- Filled missing `Embarked` with mode

### 5. Modeling

- Trained a Logistic Regression model using all cleaned and encoded features
- Used `train_test_split` for validation
- Achieved ~81% accuracy on the training subset

### 6. Submission

- Predicted on the test dataset
- Exported predictions in `submission.csv`

## Requirements

- pandas
- numpy
- seaborn
- matplotlib
- scikit-learn

## How to Run

1. Place `train.csv` and `test.csv` in the working directory
2. Run the main script
3. `submission.csv` will be created with the final predictions

## Output Format

`submission.csv` contains:

| PassengerId | Survived |
|-------------|----------|
| 892         | 0        |
| 893         | 1        |
| ...         | ...      |

