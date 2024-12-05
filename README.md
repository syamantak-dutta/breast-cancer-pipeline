# Breast Cancer Classification Project

This project leverages machine learning techniques to classify breast cancer tumors as either malignant or benign using the Wisconsin Breast Cancer Database from the UCI Machine Learning Repository. The project employs various classification algorithms to identify the most effective model for accurate tumor classification.

## Dataset

The dataset consists of 569 instances, each characterized by 32 features related to tumor characteristics. The key attributes are as follows:

- **Diagnostic Label**: Categorical variable indicating if a tumor is malignant (M) or benign (B).
- **Mean Values**: Quantitative measurements of tumor characteristics, including radius, texture, perimeter, area, smoothness, compactness, concavity, concave points, symmetry, and fractal dimension.
- **Standard Error Values**: Measures of variability or uncertainty associated with the mean values.
- **Worst or Largest Values**: Extreme values for each measurement that capture the most severe aspects of tumor growth.
- **Unique Identifier (id)**: Excluded from the analysis since it does not contribute to the predictive model.

The dataset was split into:
- **Training Set**: 60%
- **Validation Set**: 20%
- **Test Set**: 20%

## Data Preprocessing

Data preprocessing steps were implemented to ensure the quality and reliability of the analysis:

1. **Outlier Detection and Removal**: Using the Interquartile Range (IQR) method to eliminate outliers.
2. **Feature Engineering**: New features were derived from existing ones, such as:
   - Area-perimeter ratio
   - Radius-perimeter ratio
   - Concavity-perimeter ratio
   - Differences between worst and mean values for radius, perimeter, and area
   - Form factor and elongation factor
3. **Categorical Encoding**: The 'Diagnosis' column was converted from categorical to numerical values.
4. **Feature Scaling**: Data normalization to ensure all features contribute equally to the model.

## Algorithms Used

Several machine learning algorithms were evaluated for their performance in predicting breast cancer diagnoses:

### 1. Logistic Regression
- **Description**: A statistical method for binary classification, useful for predicting the probability of a binary outcome (malignant or benign). Logistic regression minimizes cross-entropy loss using gradient descent.
- **Model Outcome**: Provides a basic understanding of the relationship between tumor characteristics and diagnosis.

### 2. K-Nearest Neighbors (KNN)
- **Description**: A non-parametric classification algorithm that classifies a new data point based on the majority class of its 'k' nearest neighbors. KNN is accurate but computationally expensive for large datasets.

### 3. Support Vector Machine (SVM)
- **Description**: A classifier that finds the optimal hyperplane to separate different classes. Using kernel functions, SVM maps data to higher-dimensional spaces to better separate the classes.

### 4. Decision Tree
- **Description**: A tree-based model that makes decisions based on feature values. It recursively splits the data using a criterion like Gini impurity or information gain.

### 5. Random Forest
- **Description**: An ensemble method that combines multiple decision trees trained on random subsets of the data to improve prediction accuracy and reduce overfitting.

### 6. Voting Classifier
- **Description**: An ensemble method that combines the predictions of multiple models (Logistic Regression, KNN, SVM, Decision Tree, Random Forest). The final prediction is determined by a majority vote from the individual classifiers. This model achieved the highest recall score, making it the most effective for this application.

## Model Evaluation

The performance of each model was evaluated using the following metrics:
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**

The Voting Classifier was selected as the final model due to its superior recall score, which is crucial for minimizing false negatives in medical diagnostics.

## Requirements

- Python 3.x
- `pandas`
- `numpy`
- `scikit-learn`
- `matplotlib`
- `seaborn`

## Usage

1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/breast-cancer-classification.git
   cd breast-cancer-classification

