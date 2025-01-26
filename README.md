# Sampling-Garima-102203385
This project analyzes the impact of different sampling techniques on the performance of machine learning models for credit card fraud detection dataset.

## Dataset
The dataset used in this project is ```Creditcard_data.csv``` , a Credit Card Fraud Detection dataset, containing information about credit card transactions and a target variable (Class) where 0 represents a non-fraudulent transaction and 1 represents a fraudulent transaction. The dataset contains 772 rows and 31 columns, including features such as transaction time, amount, and various anonymized features (V1, V2, ..., V28). The class distribution in the dataset is highly imbalanced, with only 9 fraudulent transactions (1.17%) and 763 non-fraudulent transactions (98.83%). 

## Workflow
****1. Data Loading and Exploration:****
- Loads the dataset and displays basic information about it.
- Visualizes the class distribution, which is highly imbalanced.

****2. Class Balancing with SMOTE:****
- Balances the dataset using the SMOTE (Synthetic Minority Over-sampling Technique) to generate synthetic data for the minority class.

****3. Sampling Techniques:****
- Applies various sampling techniques to create different subsets of the data, including:
  
   - Simple Random Sampling
   - Systematic Sampling
   - Stratified Sampling
   - Cluster Sampling
   - Bootstrap Sampling

****4. Model Evaluation:****
- Trains and evaluates several machine learning models using 80% of each sample for training and the remaining 20% for testing:
   - Random Forest
   - Logistic Regression
   - Support Vector Machine (SVM)
   - Decision Tree
   - K-Nearest Neighbors (KNN)

- Compares model performance on each sampled dataset using accuracy as the evaluation metric.

****5. Results:****
- Displays the accuracy results for each model across different sampling techniques.
- Stores the result in ```model_accuracies.csv```.

## Observations

****1. Stratified Sampling:****
- Delivered consistently high performance for models like Logistic Regression and SVM, which are sensitive to imbalanced datasets.
- Ensured that both fraud and non-fraud cases were well-represented in training and testing datasets.
  
****2. Bootstrap Sampling:****
- Improved the robustness and stability of ensemble models like Random Forest.
- Helped Decision Trees avoid overfitting by training on varied samples.
  
****3. Simple and Systematic Sampling:****
- Showed acceptable results but lacked the diversity needed for models to generalize well in imbalanced datasets.
- Performance was inconsistent for models like KNN, which are sensitive to sampling bias.

****4. Cluster Sampling:****
- Performance was heavily dependent on how clusters were formed.
- Worked better for Random Forest and Decision Trees due to their inherent ability to handle variability.

****5. Model-Specific Trends:****
- Logistic Regression and SVM excelled with Stratified Sampling.
- Random Forest showed minimal sensitivity to the sampling method and performed consistently well.
- KNN struggled with Simple Sampling but improved with Bootstrap and Stratified Sampling.

## Conclusion
- Stratified Sampling is the most effective technique for handling class imbalance, particularly for models sensitive to class proportions like Logistic Regression and SVM.
- Bootstrap Sampling enhances the stability of models like Random Forest and Decision Trees by introducing diversity in training samples.
- Ensemble models like Random Forest are less dependent on sampling techniques and provide reliable performance across methods.
- Simple and Systematic Sampling are easy to implement but may not be suitable for highly imbalanced datasets, as they lack diversity and may introduce bias.
