# 🚁 Drone Detection System using ESP32 & NRF24L01

A real-time RF-based drone detection system that utilizes two ESP32 boards with NRF24L01 transceivers to monitor 2.4 GHz RF activity. The system detects drone-like RF transmission patterns, processes the collected data, and visualizes the results through a Python desktop application.

## 📌 Overview

This project consists of three major components:

1. **Drone Simulator (ESP32 Transmitter)** – Simulates drone-like RF transmissions.
2. **RF Sniffer (ESP32 Receiver)** – Scans RF channels and measures signal activity.
3. **Python Desktop Application** – Processes incoming RF data, detects drone activity, and provides real-time visualization.


## ✨ Features

- Real-time RF signal monitoring
- 8-channel RF spectrum scanning
- RF energy detection using NRF24L01 RPD (Received Power Detector)
- Live signal visualization using PyQtGraph
- Interactive desktop GUI built with PyQt5
- Multi-threaded serial communication
- Drone activity detection with visual and audio alerts
- JSON-based communication between ESP32 and Python application


## 🏗️ System Architecture

```
             ESP32 + NRF24L01
          (Drone Simulator)
                    │
       Generates RF Transmissions
                    │
             2.4 GHz RF Signal
                    │
────────────────────────────────────
                    │
          ESP32 + NRF24L01
           (RF Sniffer)
                    │
      Detects RF Energy (RPD)
                    │
        Sends JSON via Serial
                    │
────────────────────────────────────
                    │
      Python Desktop Application
                    │
     Signal Processing & Detection
                    │
      Live Graph + Detection Alert
```

---
## 🛠️ Hardware Components

- ESP32 Development Board ×2
- NRF24L01+ RF Module ×2
- USB Cables
- Jumper Wires
- Computer (Windows/Linux)


## 💻 Software & Technologies

### Embedded
- C++
- Arduino IDE
- ESP32
- NRF24L01
- RF24 Library
- SPI Communication

### Desktop Application
- Python
- PyQt5
- PyQtGraph
- PySerial
- JSON
- Multithreading


## 📂 Project Structure

Drone-Detection-System/
│
├── firmware/
│   ├── receiver/
│   │   └── receiver.ino
│   │
│   └── transmitter/
│       └── transmitter.ino
│
├── desktop_app/
│   └── main.py
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/Saimadhavguntur/Drone-Detection-System.git
```

---

### 2. Install Python dependencies

```bash
pip install -r requirements.txt
```

### 3. Upload ESP32 Firmware

Upload:

- `firmware/transmitter/transmitter.ino` → Drone Simulator ESP32
- `firmware/receiver/receiver.ino` → RF Sniffer ESP32


### 4. Connect Receiver ESP32

Update the COM port in `main.py` if required:

```python
SerialThread("COM13")
```

Replace **COM13** with your ESP32 serial port.


### 5. Run the Application

```bash
python main.py
```


## 📊 Working Principle

1. The transmitter ESP32 generates drone-like RF transmissions.
2. The receiver ESP32 scans predefined RF channels.
3. RF activity is measured using the NRF24L01 Received Power Detector (RPD).
4. The receiver sends normalized channel data to the PC through serial communication.
5. The Python application processes the data and visualizes RF activity in real time.
6. When drone-like RF patterns are detected, the application displays a visual alert and plays an audio notification.


## 📸 Screenshots

### Desktop Application

> *(Add your GUI screenshot here)*

### Hardware Setup

> *(Add a photo of your ESP32 + NRF24L01 setup here)*


## 🚀 Future Improvements

- Machine Learning based RF classification
- Automatic drone type identification
- Higher channel scanning resolution
- GPS-based drone localization
- Cloud logging and monitoring
- Web dashboard integration

## 👨‍💻 Author

**Sai Madhav Guntur**

- GitHub: https://github.com/Saimadhavguntur.
