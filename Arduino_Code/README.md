# Source Code

This folder contains the complete firmware, machine learning model, and training scripts used for the ECG Arrhythmia Detection System.


## Features

- Real-time ECG acquisition using AD8232
- 250 Hz sampling frequency
- Signal normalization
- TensorFlow Lite Micro inference
- CNN-based heartbeat classification
- Serial monitor prediction output
- Lightweight implementation optimized for ESP32

## Software Requirements

- Arduino IDE
- Google Collab
- TensorFlow
- TensorFlow Lite
  

## Output

After successful deployment, the ESP32 continuously acquires ECG data and classifies each heartbeat into one of the supported arrhythmia classes.
