# 🔐 Intelligent Layered Smart Door Lock System (MicroPython + Raspberry Pi Pico W)

## 📌 Project Overview

This project implements a **Smart Door Lock System** using a **Raspberry Pi Pico W** running **MicroPython**, integrating **HOG-based face recognition (off-device processing)**, **OTP-based fallback authentication**, and **real-time intruder alerts**. It features **multi-layered security** suitable for residential and commercial automation.

---

## 💡 Key Features

- 🎦 Face Recognition (pre-trained encoding using HOG - performed externally and stored in MicroPython-readable format)
- 🟢 OTP Authentication via GSM fallback when face recognition fails
- 📏 Ultrasonic detection for presence sensing
- 🔐 Relay-based solenoid lock control
- 🚨 Buzzer alert on unauthorized access attempts
- 📲 SMS-based intrusion alerts using GSM
- 🔴🟢 Real-time feedback using LEDs
- ⚡ Lightweight and cost-effective using MicroPython

---

## 🧰 Hardware Components

| Component         | Description                              |
|-------------------|------------------------------------------|
| Raspberry Pi Pico W | Wi-Fi enabled microcontroller board    |
| Pi Camera (external Pi or used in training) | For training facial data |
| BME680 Sensor     | Environment monitoring (optional)        |
| Ultrasonic Sensor | To detect proximity and trigger system   |
| 4x4 Keypad        | OTP input interface                      |
| GSM Module (SIM800L) | For sending OTP and alerts via SMS    |
| Relay Module + Solenoid | Controls the door lock              |
| LEDs (Red & Green)| Authentication status indicators         |
| Buzzer            | Audible intruder alert                   |

---

## ⚙️ System Workflow

1. **User Detected**:
   - Ultrasonic sensor triggers the system when someone approaches.

2. **Face Recognition Phase**:
   - External Pi system captures image, performs HOG-based face recognition.
   - Encoded data sent (or preloaded) to Pico W for identity verification.

3. **OTP Phase (Fallback)**:
   - If face not recognized, Pico W sends OTP via GSM module.
   - User enters OTP on keypad.
   - On success → unlocks solenoid lock.  
   - On multiple failures → buzzer alert + SMS sent to owner.

4. **Access Logging & Feedback**:
   - Green LED: Access granted.
   - Red LED + Buzzer: Access denied/intruder alert.

---

## 📂 Folder Structure (Typical)

