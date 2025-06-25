# 🔐 Intelligent Layered Smart Door Lock System (MicroPython + Raspberry Pi)

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

---

## 🛠️ How to Run

1. **Flash MicroPython** to your Raspberry Pi Pico W using [Thonny IDE](https://thonny.org/).
2. **Upload Files**:
   - Use Thonny’s File Manager to upload `.py` scripts.
3. **Connect Components** according to your circuit diagram.
4. **Run `main.py`** from Thonny or auto-start via `boot.py`.

---

## ✅ MicroPython Libraries Required

- `machine` – GPIO control
- `serial` - Communicate with Controller through UART
- `time` – Delays and timestamps  
- `random` – OTP generation  
- `face recognition` - Detecting and Recognising Face
- `pickle` - Saving and Loading Python Objects
- `cv2` - Caputuring Facial Features
- `uart` – GSM module communication  

---

## 🧪 Testing Scenarios

| Scenario                        | Outcome                          |
|---------------------------------|----------------------------------|
| Authorized face recognized      | Door unlocks                     |
| Face not recognized → OTP       | User receives SMS, unlocks on success |
| Multiple wrong OTPs             | Buzzer activates, SMS alert sent |
| No person in range              | System idle                      |

---

## 🔮 Future Improvements

- 📱 Mobile app or web UI for door control and logs
- ☁️ Cloud storage for access logs and face recognition
- 🔋 Battery backup for power failure scenarios
- 🤖 Deep Learning model (if offloaded to Pi 4 or Jetson Nano)
- 🛡️ Anti-spoofing with liveness detection (e.g., blink or depth sensing)

---

## 📜 References

- [MicroPython Official Docs](https://docs.micropython.org/)
- [face_recognition Python Library](https://github.com/ageitgey/face_recognition)
- SIM800L GSM Module AT Commands

---

## 👥 Contributors

- [Gopikrishna K (CB.EN.U4ELC22012)](https://github.com/vcgopi2k04)  
- [Harikrishnan Miraj (CB.EN.U4ELC22014)](https://github.com/hxrik)
- Jaisrihari G (CB.EN.U4ELC22015)  
- [Nandan Rajesh (CB.EN.U4ELC22063)](https://github.com/nandanrajesh)  

---

## 🏫 Institution

**Department of Electrical and Electronics Engineering**  
**Amrita School of Engineering, Coimbatore**  
**Amrita Vishwa Vidyapeetham**

---



