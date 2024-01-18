North Sea Well Log Analysis Project

This project involves the analysis of well log data from the North Sea. The raw data, provided in .las files,
was processed using the lasio Python library and subsequently transformed into a Pandas DataFrame for analysis. 
The project includes data cleaning and preprocessing, exploratory data analysis (EDA), visualization, and t
he application of machine learning models for lithology classification.

Project Structure
The project is organized into the following sections:
data: Contains the raw .las files downloaded from the North Sea well logs.
notebooks: Includes Jupyter notebooks used for the data analysis and model evaluation.
README.md: The main documentation file providing an in-depth overview of the project, the steps involved, and the results obtained.
Data Loading
The well log data was loaded using the lasio Python library, converting the .las files into a Pandas DataFrame.

Cleaning and Preprocessing
1. Standardization and Normalization
To ensure consistent scales across features, standardization and normalization techniques were applied.

2. Handling Null Values
Null values in the dataset were addressed using the interpolation method, providing estimates based on surrounding data points.

3. Removing Outliers
Outliers, which could distort the analysis, were identified and removed from the dataset.

Exploratory Data Analysis (EDA)
1. Check Shape and Size
Basic information about the data, such as its shape and size, was examined to understand the overall structure.

2. Correlation Analysis
Correlation between different features was investigated, and a correlation matrix was visualized to identify patterns and relationships in the data.
The range of correlation coefficients is between -1 and 1, where:

1 indicates a perfect positive correlation,
-1 indicates a perfect negative correlation, and
0 indicates no correlation.
Now, let's analyze the correlation matrix:

DEPTH vs. Other Variables:

LITHOLOGY (Correlation: -0.495): There is a moderate negative correlation between DEPTH and LITHOLOGY, indicating that as DEPTH increases, LITHOLOGY tends to decrease.
ROP (Correlation: -0.299): A weak negative correlation between DEPTH and ROP suggests a slight decrease in ROP as DEPTH increases.
RDEP (Correlation: 0.095): A very weak positive correlation between DEPTH and RDEP.
RMED (Correlation: 0.110): Similar to RDEP, a very weak positive correlation between DEPTH and RMED.
DTC (Correlation: -0.855): A strong negative correlation between DEPTH and DTC, indicating a significant inverse relationship.
NPHI (Correlation: 0.703): A strong positive correlation between DEPTH and NPHI, suggesting a substantial positive relationship.
PEF (Correlation: -0.807): A strong negative correlation between DEPTH and PEF, indicating a significant inverse relationship.
GR (Correlation: 0.058): A very weak positive correlation between DEPTH and GR.
RHOB (Correlation: -0.373): A moderate negative correlation between DEPTH and RHOB.
DRHO (Correlation: -0.740): A strong negative correlation between DEPTH and DRHO.
LITHOLOGY vs. Other Variables:

ROP (Correlation: 0.144): A weak positive correlation between LITHOLOGY and ROP.
RDEP (Correlation: -0.064): A weak negative correlation between LITHOLOGY and RDEP.
RMED (Correlation: -0.069): A weak negative correlation between LITHOLOGY and RMED.
DTC (Correlation: 0.390): A moderate positive correlation between LITHOLOGY and DTC.
NPHI (Correlation: -0.222): A moderate negative correlation between LITHOLOGY and NPHI.
PEF (Correlation: 0.616): A strong positive correlation between LITHOLOGY and PEF.
GR (Correlation: 0.262): A moderate positive correlation between LITHOLOGY and GR.
RHOB (Correlation: 0.358): A moderate positive correlation between LITHOLOGY and RHOB.
DRHO (Correlation: 0.562): A strong positive correlation between LITHOLOGY and DRHO.
Comparisons between Other Variables:

Strong negative correlation between DTC and DEPTH (-0.855) indicates a significant inverse relationship.
Strong positive correlation between NPHI and PEF (0.703) suggests a substantial positive relationship.
Strong negative correlation between DEPTH and PEF (-0.807) indicates a significant inverse relationship.

Visualization
Individual datasets were visualized using subplots in Matplotlib to provide a comprehensive view of each lithology in each well.

Data Merging and Mapping
The five datasets were merged into one after necessary cleaning. The lithology values, originally in a range of 0-10, 
were mapped to confirm the class distribution using a histogram.

Data Splitting and SMOTE
The data was split into training and testing sets, and Synthetic Minority Over-sampling Technique (SMOTE) was applied to address class imbalance.

Decision Tree Model:
Confusion Matrix:
The confusion matrix for the Decision Tree model provides a detailed breakdown of predicted and actual class values. It reveals the following:

True Positives (TP): 10847 instances were correctly classified as their actual class.
True Negatives (TN): The diagonal values where the predicted and actual classes match (e.g., 2499 instances correctly classified as not the second class).
False Positives (FP): Instances where the model predicted a class, but the actual class was different (e.g., 22 instances predicted as the first class but were not).
False Negatives (FN): Instances where the model failed to predict a class that was present (e.g., 73 instances not predicted as the third class but were).
Precision, Recall, and F1 Score:
Precision (Positive Predictive Value): The precision of 90.5% indicates that when the model predicts a certain class, it is correct 90.5% of the time.

Recall (Sensitivity or True Positive Rate): The recall of 85.5% signifies that the model correctly identifies 85.5% of the instances belonging to a particular class.

F1 Score: The F1 score of 87.1% is the harmonic mean of precision and recall. It provides a balanced measure between the two and indicates the overall effectiveness of the model.

Accuracy:
The accuracy of 96.32% represents the overall correct classification rate of the model. While accuracy is a crucial metric, it might not be sufficient in cases of imbalanced datasets.

Random Forest Model:
Confusion Matrix:
The confusion matrix for the Random Forest model reflects similar metrics to the Decision Tree model but with different counts:

True Positives (TP): 10957 instances were correctly classified as their actual class.
True Negatives (TN): Instances correctly classified as not belonging to a specific class.
False Positives (FP): Instances wrongly predicted as belonging to a certain class.
False Negatives (FN): Instances not predicted as belonging to a specific class but actually do.
Precision, Recall, and F1 Score:
Precision (Positive Predictive Value): The precision of 95.6% indicates a high level of confidence in the model's positive predictions.

Recall (Sensitivity or True Positive Rate): The recall of 86.5% signifies that the model captures a significant portion of instances belonging to a particular class.

F1 Score: With an F1 score of 90.1%, the Random Forest model achieves a good balance between precision and recall.

Accuracy:
The accuracy of 97.51% for the Random Forest model demonstrates its ability to correctly classify instances, surpassing the Decision Tree model.

Model Comparison:
Accuracy:

Decision Tree: 96.32%
Random Forest: 97.51%
The Random Forest model exhibits a higher accuracy, indicating that it makes fewer overall mistakes compared to the Decision Tree model.

Precision:

Decision Tree: 90.5%
Random Forest: 95.6%
The Random Forest model has a higher precision, suggesting that it is more reliable when predicting positive instances.

Recall:

Decision Tree: 85.5%
Random Forest: 86.5%
Both models have similar recall values, indicating their ability to capture a substantial portion of true positive instances.

F1 Score:

Decision Tree: 87.1%
Random Forest: 90.1%
The Random Forest model achieves a higher F1 score, signifying a better balance between precision and recall.
