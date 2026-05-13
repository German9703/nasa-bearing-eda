# NASA IMS Bearing Dataset | Predictive Maintenance EDA & ML Classifier

## Overview
End-to-end predictive maintenance project using the NASA IMS bearing vibration dataset.
4 bearings were run at 2000 RPM until failure. This project covers the full pipeline,
from raw signal analysis to a machine learning classifier that attempts to predict
bearing degradation across multiple test runs.

## Key Findings
Kurtosis and Crest Factor spike before RMS, making them superior early warning indicators.
Bearing 3 in Test 1 shows classic progressive failure; Bearings 1 and 2 show sudden late-stage degradation.
The frequency spectrum of the failure bearing shifts from flat and distributed to concentrated
energy peaks as damage develops.
A Random Forest classifier trained on Test 1 performed well within that test but failed to
generalize to Test 2, scoring AUC values near 0.5 with fixed time-based labels and 0.155
with data-driven labels; the latter indicating the model was confidently predicting the wrong class.
This exposes the central challenge of predictive maintenance in practice; a model trained on
one machine does not transfer cleanly to another, even of the same type and under similar conditions.
Solving this properly would require training data from multiple machines, domain adaptation
techniques, or an unsupervised approach that requires no labeled data at all.

## Project Structure
Notebook 1 | Data loading and cleaning
Notebook 2 | Statistical analysis, RMS and kurtosis over time
Notebook 3 | Time domain feature engineering, RMS, kurtosis, crest factor, peak-to-peak, std dev
Notebook 4 | Frequency domain analysis, FFT and spectral energy tracking
Notebook 5 | ML failure classifier, Random Forest, confusion matrix, ROC curve, feature importance
Notebook 6 | Generalization attempt with fixed time-based labels across Tests 2 and 3
Notebook 7 | Improved data-driven labeling using 3 sigma baseline deviation

## Dataset
NASA IMS Bearing Dataset, official source:
https://data.nasa.gov/dataset/ims-bearings/resource/7adad32f-5984-4a38-b1e3-e0dd2e462dc8
Collected by the Center for Intelligent Maintenance Systems (IMS), University of Cincinnati.
Test 1 used for training, Tests 2 and 3 used for generalization evaluation.
43 million rows in Test 1, approximately 1 second per file, 20,480 Hz sampling rate.

## Methods
Time domain features | RMS, Kurtosis, Crest Factor, Peak-to-Peak, Std Dev
Frequency domain | FFT, Spectral Energy tracking over time
Machine learning | Random Forest classifier with StandardScaler pipeline
Labeling strategies | Fixed 80|20 time threshold and data-driven 3 sigma baseline deviation
Evaluation | Confusion matrix, classification report, ROC curve, feature importance, AUC

## How to Run
git clone https://github.com/German9703/nasa-bearing-eda
cd nasa-bearing-eda
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
Add dataset folders to data/ from the NASA link above
Open notebooks in order in VSCode

## Reference
Hai Qiu, Jay Lee, Jing Lin, and Gang Yu. "Wavelet Filter-based Weak Signature
Detection Method and its Application on Roller Bearing Prognostics."
Journal of Sound and Vibration, 2006.