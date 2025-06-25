# OpenLab
# Intelligent Layered Smart Door Lock System using Raspberry Pi

## 📌 Project Overview

This project implements a **Smart Door Lock System** using a Raspberry Pi, combining **HOG-based Face Recognition**, **OTP verification**, and **ultrasonic sensing** for secure and automated access control. Designed for residential, commercial, and high-security environments, the system provides a **multi-layered authentication** mechanism with real-time alerts and intruder detection.

---

## 🔧 Features

- 🎦 **Face Recognition** using the HOG algorithm with the `face_recognition` library.
- 📲 **OTP Verification** via GSM when face recognition fails.
- 📷 **Ultrasonic Sensor** triggers face detection on user presence.
- 🔐 **Relay-controlled Solenoid Lock** for access control.
- 🔊 **Intruder Alerts** using Buzzer and SMS notifications.
- 🔴🟢 **LED Indicators** for authentication status.
- 🔁 **Fallback Mechanism** with retry limits and temporary lockout.

---

## 🧰 Components Used

| Hardware                     | Description                             |
|-----------------------------|-----------------------------------------|
| Raspberry Pi (any model with GPIO) | Main control unit              |
| Pi Camera                   | For capturing real-time face images     |
| Buzzer                      | Alerts on multiple failed attempts      |
| GSM Module                  | Sends OTPs and alerts                   |
| 4x4 Keypad                  | Input for OTP-based verification        |
| Ultrasonic Sensor           | Detects presence of individuals         |
| Relay + Solenoid Lock       | Physical door locking mechanism         |
| LEDs (Green/Red)            | Authentication feedback                 |

---

## 🧠 Methodology

1. **Motion Detection**: Ultrasonic sensor detects someone at the door.
2. **Face Recognition**:
    - Image is captured via Pi Camera.
    - Facial features extracted via HOG.
    - Compared to stored encodings.
    - If matched → unlock door, log access.
3. **Fallback (OTP)**:
    - On face mismatch, OTP is sent via GSM.
    - User enters OTP using 4x4 Keypad.
    - On correct input → unlock door.
4. **Security Alert**:
    - After several failed attempts, buzzer activates.
    - Owner receives SMS alert of intrusion.

---

## 🖥️ Software Requirements

- Python 3.x
- `face_recognition`
- `OpenCV`
- `numpy`
- `pickle`
- Raspberry Pi OS (Lite or Desktop)
- GSM-compatible libraries (`serial`, `pyserial`)
- GPIO library for Raspberry Pi

---

## 🧪 How to Run

1. **Clone the Repository**
   ```bash
   git clone https://github.com/yourusername/smart-door-lock-system.git
   cd smart-door-lock-system



