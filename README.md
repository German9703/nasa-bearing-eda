# NASA IMS Bearing Dataset — Predictive Maintenance EDA

## Overview
Exploratory data analysis of the NASA IMS bearing vibration dataset. 
4 bearings were run at 2000 RPM until failure. This project extracts 
time and frequency domain features to identify degradation patterns 
and early failure indicators.

## Key Findings
- Kurtosis and Crest Factor spike before RMS — making them superior early warning indicators
- Bearing 3 shows classic progressive failure; Bearings 1 and 2 show sudden late-stage degradation
- Frequency spectrum of the failure bearing shows concentrated energy peaks near failure vs flat early-stage spectrum

## Dataset
NASA IMS Bearing Dataset: https://data.nasa.gov/dataset/ims-bearings/resource/7adad32f-5984-4a38-b1e3-e0dd2e462dc8  
Test 1 used — 43 million rows, ~1 second per file, 20,480 Hz sampling rate

## Reference
Hai Qiu, Jay Lee, Jing Lin, and Gang Yu. "Wavelet Filter-based Weak Signature 
Detection Method and its Application on Roller Bearing Prognostics." 
Journal of Sound and Vibration, 2006.

## Methods
- Time domain features: RMS, Kurtosis, Crest Factor, Peak-to-Peak, Std Dev
- Frequency domain: FFT, Spectral Energy tracking over time
- Tools: Python, NumPy, Pandas, Matplotlib

## How to Run
git clone https://github.com/German9703/nasa-bearing-eda
cd nasa-bearing-eda
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
# Add dataset to data/1st_test/ from NASA link above
# Open notebooks in order in VSCode

## Next Steps
- Build an ML classifier to predict failure using extracted features
- Explore Test 2 and Test 3 for generalizations