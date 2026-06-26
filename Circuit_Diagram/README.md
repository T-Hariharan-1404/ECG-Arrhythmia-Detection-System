# Hardware Design

This folder contains the circuit diagram and hardware connections for the ECG Arrhythmia Detection System.

## Hardware Components

- ESP32 Development Board
- AD8232 ECG Sensor
- ECG Electrodes
- Breadboard
- Jumper Wires
- 100 µF Capacitor
- 0.1 µF Capacitor
- USB Power Supply

## Connections

### AD8232

| AD8232 | ESP32 |
|---------|-------|
| OUTPUT | GPIO34 |
| GND | GND |
| 3.3V | 3.3V |

The AD8232 amplifies and filters the ECG signal before it is sampled by the ESP32 ADC.
