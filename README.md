# ECG-Arrhythmia-Detection-System

##  Project Overview

ArrhythmiaNet-AI is a real-time ECG arrhythmia detection system that combines biomedical signal processing, machine learning, and embedded systems to identify abnormal heart rhythms.

The system acquires ECG signals using the AD8232 ECG sensor, processes the signals through an ESP32 microcontroller, and utilizes a TensorFlow Lite neural network model to classify heartbeats into different arrhythmia categories.

This low-cost and portable solution enables continuous cardiac monitoring and early detection of heart abnormalities.

---

##  Aim

To develop a portable and affordable real-time arrhythmia detection system using ECG signals, ESP32, and machine learning techniques for early diagnosis of cardiac abnormalities. :contentReference[oaicite:0]{index=0}

---

##  Features

- Real-time ECG signal acquisition
- ESP32-based embedded implementation
- AD8232 ECG sensor integration
- TinyML (TensorFlow Lite for Microcontrollers)
- CNN-based heartbeat classification
- Portable and low-cost design
- Wireless monitoring capability via ESP32
- Detection of abnormal cardiac rhythms

---

##  Hardware Components

- ESP32 Microcontroller
- AD8232 ECG Sensor Module
- ECG Electrodes (3-lead configuration)
- Breadboard
- Jumper Wires
- 100µF Electrolytic Capacitor
- 0.1µF Ceramic Capacitor
- USB Power Supply

---

##  Software Requirements

- Arduino IDE
- Google Colab
- Python
- TensorFlow
- TensorFlow Lite
- NumPy
- Pandas
- SciPy
- Matplotlib
- WFDB Library

---

##  System Architecture

```text
ECG Electrodes
        │
        ▼
 AD8232 ECG Sensor
        │
        ▼
      ESP32
        │
        ▼
 Signal Processing
        │
        ▼
  CNN TinyML Model
        │
        ▼
 Arrhythmia Detection
        │
        ▼
 Real-Time Prediction
```

---

##  Working Principle

The ECG electrodes capture the electrical activity of the heart. These bio-potential signals are amplified and filtered using the AD8232 ECG module. The conditioned ECG signal is then digitized using the ESP32 ADC.

The ESP32 continuously monitors ECG waveforms, extracts heartbeat information, and sends the processed data to a trained TensorFlow Lite model. The neural network classifies the heartbeat and identifies arrhythmias such as:

- Normal Rhythm
- Supraventricular Ectopic Beat (SVEB)
- Ventricular Ectopic Beat (VEB)
- Other Abnormal Rhythms

The ESP32 provides real-time monitoring and prediction capabilities. :contentReference[oaicite:1]{index=1}

---

##  Dataset

### MIT-BIH Arrhythmia Database

Records Used:

```python
['100', '101', '103', '105', '106',
 '107', '108', '109', '111', '112']
```

Database Source:
- PhysioNet MIT-BIH Arrhythmia Database

---

##  Machine Learning Model

### Model Architecture

The system uses a lightweight 1D Convolutional Neural Network (CNN) optimized for embedded deployment.

#### Network Structure

```text
Input ECG Signal (180 Samples)
          │
          ▼
Conv1D (8 Filters, Kernel=7)
          │
          ▼
MaxPooling1D
          │
          ▼
Dropout (0.1)
          │
          ▼
Conv1D (4 Filters, Kernel=5)
          │
          ▼
MaxPooling1D
          │
          ▼
Flatten
          │
          ▼
Dense Softmax Layer
          │
          ▼
4-Class Classification
```

---

##  Classification Categories

| Class | Description |
|---------|------------|
| 0 | Normal Beat (N) |
| 1 | Supraventricular Ectopic Beat (SVEB) |
| 2 | Ventricular Ectopic Beat (VEB) |
| 3 | Other / Fusion Beat |

---

##  Data Preprocessing

### ECG Window Parameters

| Parameter | Value |
|------------|---------|
| Window Size | 180 Samples |
| Samples Before R-Peak | 60 |
| Samples After R-Peak | 120 |

### Processing Steps

1. ECG Acquisition
2. R-Peak Detection
3. Beat Segmentation
4. Normalization
5. Reshaping for CNN Input
6. Model Training

---

##  Model Training

### Dataset Split

- Training: 80%
- Validation: 10%
- Testing: 10%

### Training Parameters

| Parameter | Value |
|------------|---------|
| Epochs | 30 |
| Batch Size | 64 |
| Optimizer | Adam |
| Loss Function | Sparse Categorical Crossentropy |

---

## 📊 Deployment Constants

```cpp
MIN_VAL = -3.7149999141693115
MAX_VAL = 3.4649999141693115

WINDOW_SIZE = 180
NUM_CLASSES = 4
```

These values are used for real-time normalization of ECG data before inference. :contentReference[oaicite:2]{index=2}

---

##  Real-Time Sampling

### Sampling Frequency

```cpp
250 Hz
```

### ADC Configuration

```cpp
ADC_PIN = GPIO34
ADC_RESOLUTION = 12-bit
```

The ESP32 collects ECG samples every 4 milliseconds and stores them in a buffer for inference.

---

##  Sample Output

```text
TFLite Model Initialized Successfully.
Sampling Timer Started at 250 Hz.

Prediction: 0 (Prob: 98.7%)
NORMAL RHYTHM (N)

Prediction: 2 (Prob: 85.2%)
VENTRICULAR ECTOPIC ALERT (V)

Prediction: 0 (Prob: 99.1%)
NORMAL RHYTHM (N)
```

:contentReference[oaicite:3]{index=3}

---

##  Applications

- Smart Healthcare Systems
- Remote Patient Monitoring
- Wearable Health Devices
- Telemedicine
- Hospital Monitoring Systems
- Preventive Cardiology
- IoT-Based Medical Devices

---

##  Future Enhancements

- Mobile Application Integration
- Cloud-Based ECG Monitoring
- Multi-Lead ECG Analysis
- Advanced Deep Learning Models
- Real-Time Alert Notifications
- IoT Dashboard Integration


---

##  Conclusion

This project demonstrates an efficient and affordable solution for real-time ECG arrhythmia detection using ESP32, AD8232, and TinyML. By combining biomedical signal processing with machine learning, the system enables continuous cardiac monitoring and early identification of abnormal heart rhythms, making it suitable for next-generation wearable healthcare applications. :contentReference[oaicite:4]{index=4}

---
