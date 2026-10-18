# Report Summary: Sensor Anomaly Detection

This summary is based on the supplied document, **Completed Anomaly Detection Report.docx**. It records the results as reported in that document; they have not been independently reproduced here.

## Dataset and target

The report describes multivariate sensor data with date/time fields, mote ID, temperature, humidity, light, voltage, and an `anomaly_label`. The notebook's label-generation rule marks a row anomalous when Temperature is above 100 or below -20, Humidity is below 0 or above 100, or Voltage is below 2.1. The selected model features are Temperature, Humidity, Light, and Voltage.

## Individual-model results reported

| Model | Accuracy | Precision | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|---:|
| Random Forest | 1.0000 | 1.0000 | 1.0000 | 1.0000 | 1.0000 |
| Extra Trees | 0.9994 | 0.9998 | 0.9965 | 0.9981 | 0.9982 |
| XGBoost | 0.9995 | 0.9985 | 0.9988 | 0.9987 | 1.0000 |
| LightGBM | 0.9999 | 0.9998 | 0.9994 | 0.9996 | 1.0000 |

The report also describes hard-voting and soft-voting ensemble experiments. It gives hard-voting accuracy as approximately 0.99986 in one section and approximately 0.99996 in another.

## Interpretation and limitations

These are values transcribed from the supplied report, not a verified benchmark. The report contains inconsistencies between some narrative explanations, tables, confusion matrices, and its concluding paragraph. The notebook should be rerun and its outputs checked before these metrics are used in a CV, case study, or business claim.

A further methodological limitation is that the target label is generated from threshold rules applied to sensor features that are then used to train the classifiers. This creates a risk of target leakage / rule reproduction: high test scores may show that the model learned the label-generation rules rather than that it can discover independently defined real-world anomalies.

The supplied notebook refers to a dataset file named `data.txt`, but that dataset was not included with the supplied attachments.
