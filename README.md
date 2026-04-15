# Patient Monitoring and Identification System

## Overview
This project is a smart healthcare monitoring system using ESP32-CAM for facial recognition and real-time monitoring of patient vitals such as temperature, ECG, and heartbeat. The system detects abnormalities and sends alerts along with data over Wi-Fi for remote monitoring.

## Features
- Facial recognition for patient identification  
- Real-time monitoring (Temperature, ECG, Heartbeat)  
- Abnormality detection using threshold logic  
- Automatic alert system  
- Wi-Fi-based remote monitoring  

## System Architecture
```mermaid
flowchart LR
A[Capture Image] --> B[Face Detection]
B --> C{Face Recognized}

C -- No --> D[Stop]
C -- Yes --> E[Read Sensors]

E --> F[Temperature]
E --> G[ECG]
E --> H[Heartbeat]

F --> I[Compare Threshold]
G --> I
H --> I

I --> J{Abnormal}

J -- Yes --> K[Trigger Alert]
J -- No --> L[Continue Monitoring]

K --> M[Send Data WiFi]
L --> M

M --> N[End]
```
## Hardware Components
- ESP32-CAM  
- Temperature Sensor (LM35 / DS18B20)  
- Heartbeat Sensor  
- ECG Sensor  
- Power Supply  
- Breadboard & Jumper Wires  

## Circuit Diagram
          +----------------------+
          |      ESP32-CAM       |
          |                      |
          |   GPIO34 <--- Temp   |
          |   GPIO35 <--- Heart  |
          |   GPIO32 <--- ECG    |
          |                      |
          |   3.3V ----+--------+------+
          |            |        |      |
          |           Temp    Heart   ECG
          |            |        |      |
          |   GND -----+--------+------+
          +----------------------+
          
## Circuit Connections
Temperature Sensor: VCC → 3.3V, GND → GND, OUT → GPIO34  
Heartbeat Sensor: VCC → 3.3V, GND → GND, Signal → GPIO35  
ECG Sensor: VCC → 3.3V, GND → GND, Output → GPIO32  
ESP32-CAM: Powered via 5V, camera used for face detection  

## Output
- Detects patient using facial recognition  
- Monitors vital parameters in real-time  
- Sends alerts for abnormal conditions  
- Transmits data via Wi-Fi  

## Future Improvements
- Cloud integration  
- Mobile application  
- Improved accuracy and scalability  

## Author
Muskaan Husain
