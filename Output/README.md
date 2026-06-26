# Experimental Results

This folder contains the vedio taken during system testing.


## Output of ML Model

MIN_VAL, Normalisation Min,−3.7149999141693115, 
Used to normalise real-time AD8232 readings. 
MAX_VAL, Normalisation Max,3.4649999141693115, 
Used to normalise real-time AD8232 readings. 
 
 
Deployment Constants to use in your ESP32 C++ Code: 
 - Normalisation Min (MIN_VAL): -3.7149999141693115 
 - Normalisation Max (MAX_VAL): 3.4649999141693115 
 - Input Array Size: 180 
 - Output Classes: 0=Normal, 1=SVEB, 2=VEB, 3=Other
   

## Output

TFLite Model Initialized Successfully.
Sampling Timer Started.

Pred: 0 (P: 98.7%) -> NORMAL
Pred: 0 (P: 99.1%) -> NORMAL
Pred: 1 (P: 91.4%) -> SVEB
Pred: 0 (P: 97.9%) -> NORMAL
Pred: 2 (P: 85.2%) -> !!! VEB ALERT (V) !!!
Pred: 0 (P: 98.5%) -> NORMAL
Pred: 3 (P: 83.6%) -> OTHER/UNKNOWN
Pred: 0 (P: 99.0%) -> NORMAL
Pred: 1 (P: 90.8%) -> SVEB
Pred: 2 (P: 87.3%) -> !!! VEB ALERT (V) !!!
Pred: 0 (P: 98.8%) -> NORMAL

## Observations

- Stable ECG acquisition at 250 Hz
- Accurate heartbeat classification
- Low inference latency on ESP32
- Reliable TinyML deployment
- Continuous real-time monitoring
