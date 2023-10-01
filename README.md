# Diabetes Type 2 Hackathon README

## Introduction
This README provides an overview of the hackathon project focused on exploring the medical implications resulting from Type 2 Diabetes. The project aimed to build predictive models to determine if a patient will have cardiovascular complications within the next 10 years. The project involved data preprocessing, feature engineering, model building, and an innovative optimization framework to provide personalized recommendations for patients.

## Project Details
Although the project is only a prototype, this is the vision of the project as a whole.
The project was in 2 phases. First we created a ML model that is able to predict a binary variable of "will the patient have a cardiovascular implication in the next 10 years".
After that, on the second phase, we create a product that uses this model, and create a custom made plan for the patient that is both minimal and robust due to the unique kind of optimization
used as our model (refrences are added to the article used).

### Data
The dataset used for this project contained the following features:

- **id**: Unique identifier (integer).
- **age**: Age of the patient in full years (integer).
- **sex**: Gender of the patient, converted to binary: "F"=0, "M"=1.
- **is_smoking**: Smoking status, converted to binary: "YES"=1, "NO"=0.
- **cigsPerDay**: Number of cigarettes a patient usually smokes per day (continuous).
- **BPMeds**: Whether the patient was on blood pressure medication, binary.
- **prevalentStroke**: Whether the patient had previously had a stroke, binary.
- **prevalentHyp**: Whether the patient was hypertensive, binary.
- **diabetes**: Whether the patient had diabetes, binary.
- **totChol**: Total cholesterol level (continuous).
- **sysBP**: Systolic blood pressure (continuous).
- **diaBP**: Diastolic blood pressure (continuous).
- **BMI**: Body Mass Index (continuous).
- **heartRate**: Heart rate (continuous).
- **glucose**: Glucose level (continuous).
- **education**: Education level with categories: 1=“didn’t graduate high school”, 2=“graduated high school / GED”, 3=“attended college/university without graduating”, 4=" graduated from college/university" (categorical).

### Feature Creation
Four new features were created:

1. **Packs of Cigarettes**: Based on the amount in the "cigsPerDay" column.
2. **Hypertension Status**: Determined based on systolic and diastolic blood pressure.
3. **Glucose Level**: Categorized cutoffs for the glucose column.
4. **Diabetes Score2**: A simplified metric for diabetes detection, which proved highly successful.

### Handling Missing Data and Imbalance
- Missing data was handled using standard methods: Median for continuous values and Mode for categorical values.
- To address class imbalance in the binary target variable, the SMOTE (Synthetic Minority Over-sampling Technique) algorithm was used to oversample the minority class.

## Proof of Concept (POC) and Model Results
Two tree-based models, Random Forest and Gradient Boosting Tree, were employed due to their explainability in medical contexts. Model evaluation results are as follows:

#### All Data (Including SMOTE):
- Random Forest: Accuracy on test data = 0.9175, AUC = 0.9721
- Gradient Boosting Machine: Accuracy on test data = 0.9157, AUC = 0.9696

#### Clean Data (Excluding SMOTE):
- Random Forest: Accuracy on test data = 0.886, AUC = 0.8985
- Gradient Boosting Machine: Accuracy on test data = 0.8725, AUC = 0.8552

## Optimization Framework
An optimization framework was developed to actively help diabetic patients minimize their cardiovascular complications. The objective was to find the minimal changes to measured values that could reduce a patient's risk.

### Algorithm
- The optimization algorithm is capable of finding a robust, minimal, and optimal change to measured values using various models, including Decision Trees, Random Forest, XGBoost, and simple Neural Networks.

## Implementation
The project also included the implementation of the optimization framework and a simple GUI for practical application. The steps involved:

1. Sample a diabetic patient.
2. Calculate the minimal changes required for the classifier to predict a lower risk (from 1 to 0).
3. Translate these changes into actionable recommendations.
4. Generate a customized plan for diabetic patients to improve their habits and lifestyle, optimized for minimal effort and maximum benefit.

The result is a personalized plan designed to help diabetic patients avoid cardiovascular complications while minimizing lifestyle disruptions.

## Conclusion
This hackathon project successfully explored the medical implications of Type 2 Diabetes, developed predictive models, and created an innovative optimization framework for personalized patient recommendations. The application of machine learning and optimization in the medical field offers the potential to improve patient outcomes and quality of life.

## Thanks and References
We were inspired by the article "Finding Regions of Counterfactual Explanations via Robust Optimization”, 2023, Maranago et. al.
Maragano and his team we kind to create and release the RCE library for others to use.
So I would like to thank them for their idea and contribution! 
You can find their article in the refrence folder here.
