# Symptom-Based Disease Diagnosis System
Multi-class classification model that predicts the most likely disease from 132 reported symptoms across 42 disease classes — built using 3 tuned ML classifiers and CRISP-DM methodology.

#Project Overview
Misdiagnosis and delayed diagnosis are major problems in healthcare globally. This project builds a symptom-based disease prediction system that provides an instant preliminary diagnosis to support clinical decision-making.
Problem TypeMulti-Class ClassificationDatasetTraining.csv & Testing.csv — 132 binary symptom featuresTargetprognosis (42 disease classes)MethodologyCRISP-DM

#Dataset Features
132 binary symptom columns where 0 = symptom absent and 1 = symptom present. Each row represents one patient. The target column is prognosis — the name of the disease.
The dataset is perfectly balanced with equal samples per disease class, and each disease maps to a unique non-overlapping symptom combination.

#Business Understanding
A healthcare provider wants a system that, given a patient's reported symptoms, instantly returns the most likely disease and its probability. This supports general practitioners in narrowing down differential diagnoses quickly, helps prioritise specialist referrals, and serves as a first-line triage tool in resource-limited clinics.

#Pipeline (CRISP-DM)
#Data Cleaning

Dropped empty artifact column Unnamed: 133 from both train and test files
Confirmed zero null values across all 132 symptom columns
Removed duplicate rows from training data

Feature Engineering

No encoding needed — all symptom columns already binary (0/1)
No scaling needed — all features on the same scale
No train/test split needed — separate files already provided
Features (X) and target (y) split directly from both files

#Modelling — 3 classifiers tuned with GridSearchCV (5-fold CV)
ModelDetailLogistic RegressionBest model — used for final prediction and probabilitiesK-Nearest NeighborsTuned n_neighbors (1–50) and distance metricSupport Vector MachineTuned C and kernel type

#Results

All 3 models achieved 100% accuracy on both train and test sets
This is expected — each disease has a unique, non-overlapping symptom profile with no ambiguity between classes
predict_proba used to return top-5 disease probabilities for clinical use


#Sample Prediction
Symptoms present: itching, skin_rash, nodal_skin_eruptions, dischromic_patches

#Predicted Disease: Fungal Infection

#Top 5 probabilities also returned for clinical review

#Tech Stack

Language: Python
Libraries: pandas, numpy, scikit-learn, matplotlib, seaborn
Models: Logistic Regression, KNN, SVM
Techniques: CRISP-DM, GridSearchCV, Cross-Validation, Multi-Class Classification, predict_proba
