# Sensor Data Anomaly Detection with Machine Learning

**Project type:** Python / machine learning / binary classification  
**Author:** Isaac Olufemi Adewumi

## Project overview

This project explores anomaly detection in multivariate sensor readings. The report describes records containing date/time information, mote ID, temperature, humidity, light, and voltage. The modelling workflow uses the four sensor measurements—Temperature, Humidity, Light, and Voltage—to classify records as normal or anomalous.

## Models explored

The supplied notebook and report cover:
- Random Forest
- Extra Trees
- XGBoost
- LightGBM
- Ensemble classification using hard and soft voting

The report evaluates models using accuracy, precision, recall, F1-score, ROC-AUC, confusion matrices, and classification reports.

## Project files

The original files supplied for this project are intended to be organised as follows:

- `notebooks/anomaly_detection.ipynb` — original Jupyter notebook / Python analysis
- `reports/anomaly_detection_report.docx` — report describing the preprocessing, modelling, and reported results

The notebook and report still need to be uploaded to these paths. The dataset file referenced in the notebook is named `data.txt`; it was not included with the two supplied files, so the notebook will not run end-to-end until the dataset is added.

## Workflow described in the materials

1. Load sensor readings into a pandas DataFrame.
2. Forward-fill missing values and inspect/remove duplicate rows.
3. Create an `anomaly_label` using threshold rules for temperature, humidity, and voltage.
4. Use Temperature, Humidity, Light, and Voltage as model features.
5. Train and evaluate the individual classifiers.
6. Compare the individual models and explore voting-based ensembles.

## Important interpretation note

The notebook creates the target label from threshold rules applied to some of the same sensor variables later supplied to the models. This can make the classification task easier because the models may learn to reproduce those rules. The very high scores reported in the accompanying report should therefore **not** be interpreted as proof of equivalent real-world anomaly-detection performance without additional validation against independently labelled data and a leakage-aware evaluation.

The report also contains some inconsistent descriptions and metric/confusion-matrix values. Treat the figures as results reported in the supplied document until the notebook is rerun and the outputs are reconciled.

## Reproducibility

The dataset is not included in this repository yet. Before running the notebook, add the dataset only if you have the right to share it, and update the file path if necessary. Do not upload confidential or restricted data.

## Tools

Python, pandas, NumPy, scikit-learn, XGBoost, LightGBM, and Jupyter Notebook.
