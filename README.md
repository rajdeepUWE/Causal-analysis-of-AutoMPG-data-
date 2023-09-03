# Causal-analysis-of-AutoMPG-data-

Add files via upload
Below is the detailed example of the functionality of the code. I have used google COLAB IDE to run my analysis. 


Mounting Google Drive: The code starts by mounting your Google Drive, which is often done when working in a Google Colab environment to access files stored in your Google Drive.

Importing Libraries: Various Python libraries are imported, including NumPy, pandas, Matplotlib, Seaborn, and scikit-learn (a machine learning library). These libraries are commonly used for data manipulation, visualization, and machine learning tasks.

Reading the Dataset: The code reads a dataset from your Google Drive using the pandas library. This dataset is assumed to be in CSV format and contains information about vehicles, including attributes like MPG, cylinders, displacement, horsepower, etc.

Data Exploration and Preprocessing:

It explores the dataset by checking data types, summary statistics, and identifying missing values.
Box plots are used to visualize potential outliers in numeric columns.
Missing values in the "Horsepower" column are imputed with the median value.
Histograms and categorical value distributions are plotted to understand the data's distribution.
Pair plots are used to visualize relationships between different attributes.
Stratified Sampling: The dataset is split into training and testing sets using stratified sampling, ensuring that the distribution of the "Cylinders" attribute is preserved in both sets.

Feature Engineering: New attributes (features) are created based on existing attributes, and their correlation with the target variable (MPG) is checked.

Data Transformation:

The target variable (MPG) is separated from the features.
Categorical columns (e.g., "Origin") are preprocessed using one-hot encoding.
Numerical columns are scaled using StandardScaler.
Linear Regression Model: A linear regression model is trained using the prepared data.

Random Forest Regressor Model: A random forest regressor model is also trained and evaluated using cross-validation.

Hyperparameter Tuning: Grid search is performed to find the best hyperparameters for the random forest regressor model.

Feature Importance: The feature importances of the best model are calculated and displayed.

Final Model Evaluation: The final model's performance is evaluated on the test dataset, and the root mean squared error (RMSE) is calculated.

Predicting MPG: A function predict_mpg is defined to predict the MPG of a vehicle based on its configuration. This function takes a dictionary of attributes as input, preprocesses the data, and uses the final trained model to make predictions.

Installation of DoWhy and Graphviz: You start by installing the DoWhy library and the Graphviz library, which is used for visualizing causal graphs.

Importing Necessary Libraries: You import the required libraries, including DoWhy, pandas, Matplotlib, NumPy, and others.

Dataset Preparation: The code uses the data_target DataFrame, which presumably contains the dataset related to automobile attributes. The dataset is renamed to have a "Year" column instead of "Model Year" for consistency.

Defining the Causal Graph: A causal graph is defined using a directed graph format. The graph represents the assumed causal relationships between different variables. In this case, it includes the relationships between various automobile attributes (e.g., Cylinders, Displacement, Weight) and the target variable (MPG).

Causal Models and Estimations:

Several causal models are defined, each focusing on a different treatment variable (e.g., Cylinders, Displacement, Weight, Year, Horsepower, Acceleration).
For each model, the code performs the following steps:
Defines a CausalModel using the dataset, treatment, outcome, causal graph, and common causes.
Views and visualizes the causal model.
Identifies the causal estimand.
Estimates the causal effect using the linear regression method.
Prints the causal estimand and the estimated causal effect, including its significance (p-value).
Creating a Summary Table: After estimating the causal effects for each treatment variable, the code creates a summary table that includes the target variable, treatment variable, estimated causal effect, and p-value for each causal analysis.

Here's a summary of the estimated causal effects for each treatment variable:

Cylinders: Causal Effect: -1.8759, p-value: 2.0000e-15
Displacement: Causal Effect: -0.0788, p-value: 2.6785e-19
Weight: Causal Effect: -0.0096, p-value: 3.3674e-40
Year: Causal Effect: 0.7300, p-value: 2.0473e-52
Horsepower: Causal Effect: -0.1676, p-value: 1.3190e-11
Acceleration: Causal Effect: -0.1695, p-value: 8.2971e-24
These values indicate the estimated impact of each treatment variable on the target variable (MPG) and their associated statistical significance.

View my medium post on this:- https://rajdeepsarkar95.medium.com/exploring-the-causal-effects-of-automobile-attributes-on-mpg-a-data-driven-approach-fbd5f0fb294a

To learn about DoWHy library and Causal effects read this:- https://medium.com/python-in-plain-english/a-guide-to-downloading-and-installing-dowhy-in-python-jupyter-notebook-for-causal-analysis-4db2c09d22bb
