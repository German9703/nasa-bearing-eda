# NASA IMS Bearing Dataset | Predictive Maintenance EDA & ML Classifier

## Overview
End-to-end predictive maintenance project using the NASA IMS bearing vibration dataset.
4 bearings were run at 2000 RPM until failure. This project covers the full pipeline,
from raw signal analysis to a machine learning classifier that predicts bearing degradation.

## Key Findings
Kurtosis and Crest Factor spike before RMS, making them superior early warning indicators.
Bearing 3 shows classic progressive failure; Bearings 1 and 2 show sudden late-stage degradation.
The frequency spectrum of the failure bearing shifts from flat and distributed to concentrated
energy peaks as damage develops.
A Random Forest classifier trained on Bearings 1 and 2 successfully identifies degradation
in Bearing 3, a bearing it had never seen during training.

## Project Structure
Notebook 1 | Data loading and cleaning
Notebook 2 | Statistical analysis, RMS and kurtosis over time
Notebook 3 | Time domain feature engineering, RMS, kurtosis, crest factor, peak-to-peak, std dev
Notebook 4 | Frequency domain analysis, FFT and spectral energy tracking
Notebook 5 | ML failure classifier, Random Forest, confusion matrix, ROC curve, feature importance

## Dataset
NASA IMS Bearing Dataset — official source:
https://data.nasa.gov/dataset/ims-bearings/resource/7adad32f-5984-4a38-b1e3-e0dd2e462dc8
Collected by the Center for Intelligent Maintenance Systems (IMS), University of Cincinnati.
Test 1 used — 43 million rows, ~1 second per file, 20,480 Hz sampling rate

## Methods
Time domain features | RMS, Kurtosis, Crest Factor, Peak-to-Peak, Std Dev
Frequency domain | FFT, Spectral Energy tracking over time
Machine learning | Random Forest classifier with StandardScaler pipeline
Evaluation | Confusion matrix, classification report, ROC curve, feature importance
Tools | Python, NumPy, Pandas, Matplotlib, Scikit-learn

## How to Run
git clone https://github.com/German9703/nasa-bearing-eda
cd nasa-bearing-eda
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
# Add dataset to data/1st_test/ from the NASA link above
# Open notebooks in order in VSCode

## Next Steps
Generalize the model to Test 2 and Test 3 datasets.

## Reference
Hai Qiu, Jay Lee, Jing Lin, and Gang Yu. "Wavelet Filter-based Weak Signature
Detection Method and its Application on Roller Bearing Prognostics."
Journal of Sound and Vibration, 2006.