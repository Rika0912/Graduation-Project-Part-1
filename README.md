## Predicting Hazardous Near Earth Objects (NEOs)
# Project Overview
This project aims to predict whether a Near Earth Object (NEO) is hazardous based on its various features. With growing concerns around NEOs, this project focuses on using machine learning to classify objects as potentially hazardous or non-hazardous. The dataset contains observations of NEOs from 1910 to 2024, and the key target variable is is_hazardous.

The project workflow includes data cleaning, exploratory data analysis (EDA), handling imbalanced classes, model training, and evaluation. The results indicate that the Random Forest classifier performed the best in identifying hazardous NEOs.

# Table of Contents

* Data Importing and Cleaning
* Exploratory Data Analysis (EDA)
* Data Preprocessing
* Model Training and Evaluation
* Key Findings and Insights
* How to Run the Project
* Conclusion
  
# Data Importing and Cleaning
The dataset contains NEOs data from 1910 to 2024. The data import and cleaning phase involves handling missing values and duplicates to ensure data quality for model training.

# Steps:
1. Load the Dataset
The dataset was loaded using pandas, and the file path is specified.

2. Handling Missing Values
Missing values in numerical features such as absolute_magnitude, estimated_diameter_min, and estimated_diameter_max were handled using forward-fill (ffill).

3. Removing Duplicates
Duplicate rows were dropped to avoid any redundant information that might affect the model.

# Data Summary:
* The dataset contains 338,199 entries.
* The features include NEO ID, name, absolute magnitude, estimated diameter, orbiting body, relative velocity, miss distance, and whether the object is hazardous.

# Exploratory Data Analysis (EDA)
Exploratory Data Analysis (EDA) was performed to understand the distribution of variables, correlations between features, and to uncover potential patterns in the dataset.

# Key Steps:
1. Target Distribution
A count plot was created to visualize the distribution of hazardous (True) vs non-hazardous (False) objects.

2. Correlation Analysis
A heatmap was generated to understand the relationships between numerical features, such as absolute_magnitude, estimated_diameter, and relative_velocity.

3. Boxplots and Histograms
Boxplots were used to understand the distribution of features like absolute_magnitude, and histograms were used to visualize feature distributions grouped by is_hazardous.

# Insights:
* There are significantly fewer hazardous NEOs compared to non-hazardous ones.
* Certain features, like absolute_magnitude, seem to have some correlation with is_hazardous, suggesting their potential relevance in predicting hazardous NEOs.

# Data Preprocessing
In this stage, we prepared the data for modeling. Key preprocessing steps included scaling numerical features and addressing the class imbalance in the target variable (is_hazardous).

# Key Steps:
1. Train-Test Split
The data was split into training and test sets (80%-20%).

2. Feature Scaling
Numerical features were scaled using StandardScaler to normalize the data for better model performance.

3. Handling Imbalanced Classes
The target variable is_hazardous was highly imbalanced, so we applied SMOTE (Synthetic Minority Over-sampling Technique) to balance the classes in the training set.

// Result:
The training data was balanced, with an equal number of hazardous and non-hazardous samples, enabling the model to better identify hazardous NEOs.

# Model Training and Evaluation
We experimented with two machine learning models: Random Forest and Logistic Regression. The models were evaluated based on key metrics such as accuracy, precision, recall, F1-score, and the AUC-ROC curve.

# Random Forest Classifier:
* Accuracy: 98%
* Precision: 99% (Non-hazardous), 88% (Hazardous)
* Recall: 98% (Non-hazardous), 96% (Hazardous)
* F1-Score: 99% (Non-hazardous), 92% (Hazardous)
* AUC-ROC Score: 0.996

# Logistic Regression:
* Accuracy: 74%
* Precision: 98% (Non-hazardous), 31% (Hazardous)
* Recall: 72% (Non-hazardous), 88% (Hazardous)
* F1-Score: 83% (Non-hazardous), 46% (Hazardous)
* AUC-ROC Curve: 0.836

// Result:
The Random Forest Classifier outperformed Logistic Regression in distinguishing between hazardous and non-hazardous objects based on Precision, Recall, F1-Score, and AUC-ROC Curve, making it the best model for predicting hazardous NEOs.

# Key Findings and Insights
1. Imbalanced Classes: The dataset was highly imbalanced, requiring techniques like SMOTE for balancing. Addressing class imbalance significantly improved the model's performance.

2. Model Performance: The Random Forest Classifier achieved high accuracy (98%) and performed well across other metrics, making it an ideal choice for this problem.

3. Important Features: Features like absolute_magnitude, estimated_diameter, and relative_velocity played a crucial role in determining whether a NEO is hazardous.

# How to Run:
1. Clone this repository
2. Install required dataset
3. Run the Jupyter Notebook to see the full analysis.

# Conclusion
The project successfully predicts hazardous Near Earth Objects using machine learning techniques. The Random Forest model demonstrated excellent performance, and through data preprocessing and addressing class imbalances, we ensured reliable predictions. This analysis could be extended further with additional features or by incorporating more advanced models.
