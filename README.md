Predicting Clinical Dementia Ratings (CDR) using machine learning
classifiers using OASIS-1 Data

The goal of this research problem was to use publicly available
neuro-imaging data to predict CDR rating of patents in the OASIS study.
Examples of features used in predicting the CDR were Mini-Mental State
Examination Scores, Normalized Whole Brain Volume, Estimated Total
Intracranial Volume, and Atlas Scaling Factors.

F1-Macro was used as the evaluation metric for this project due to the
small number of CDR 2 and 3 classifications. Macro ensures that correct
predictions in the larger classes, such as CDR 0 and 0.5, do not
suppress poor accuracy in the rarer classes.

The repository is structured as follows.

data/ figures/ results/ report/ src/ .gitignore LICENSE.txt README.md

Requirements:

Python Version 3.12.10 numpy Version 2.2.5 pandas Version 2.2.3
matplotlib Version 3.10.1 sklearn Verison 1.6.1 shap Version 0.47.2
joblib Version 1.5.2

Environment setup:

Please use the provided environment.yaml file to reproduce the
environment

1\. Clone git clone (git url) cd (project name)

2\. Create environment conda env create -f environment.yaml conda
activate data1030

To run this project 1. Ensure the oasis_original.xlsx is in the "data"
folder 2. Run "CDR_Project_Ana_Doverspike.ipynb" from the src folder

All results will be saved to the results folder upon running the full
script.

The following models are available for immediate use
best_elastic_net_pipeline.pkl best_knn_pipeline.pkl
best_svc_pipeline.pkl best_rf_pipeline.pkl

To use any of these models, in python import joblib import os

loaded_model = joblib.load(os.path.join('results',
'best_svc_pipeline.pkl'))

new_predictions = loaded_model.predict(X_new_data)

The final_model_scores.csv provides a table of calculated F1-Scores for
Validation and Test compared to the baseline score of predicting CDR 0
for all samples.

This project is released under the MIT License, please see the
LICENSE.txt file for full details.
