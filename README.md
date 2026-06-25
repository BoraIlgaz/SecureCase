# 🔐 Secure Case - Smart Security and IoT Safe System

**Secure Case** is a smart security project that combines physical security with modern IoT technologies, offering real-time tracking and remote control capabilities. It detects unauthorized opening of the safe lid and instantly warns the user with mobile notifications.

---

## 🖼️ Project Visuals and Design

The hardware architecture and physical structure of the system are detailed below:

| **1. Circuit Diagram (P1)** | **2. Internal Design & Sensor (P2)** | **3. Overall Safe View (P3)** |
| :--- | :--- | :--- |
| ![Devre Şeması](Screenshots/p1.jpg) | ![İç Tasarım](Screenshots/p2.jpg) | ![Proje Fotoğrafı](Screenshots/p3.jpg) |
| *The electronic connection plan of the system.* | *The strategic positioning of the distance sensor.* | *The external view of the finished project.* |

---

## 🚀 Project Overview

The system constantly tracks the position of the lid through a distance sensor (p2) placed inside the safe. Any movement (opening of the lid) that occurs while the security mode is active puts the system into an alarm state.

* **Physical Warning:** An audible and visual alarm is triggered via the **Buzzer** and **LED** located on the safe.
* **IoT Tracking:** The status of the safe is instantly transmitted to the mobile application using the **MQTT** protocol.
* **Remote Control:** The security mode can be turned on and off with a single button via the mobile application.

---

## 🛠️ Technical Components

### Hardware
* **Distance Sensor (Ultrasonic):** Precisely measures the openness status of the safe lid.
* **Buzzer & LED:** Provides on-site audible and visual warnings during unauthorized access attempts.
* **Microcontroller:** Processes sensor data and connects to the cloud via Wi-Fi.

### Software
* **MQTT Protocol:** Ensures low-latency, reliable data transmission.
* **Mobile Application:** An interface designed to manage security status and receive notifications.
* **Embedded Software:** A C++ based software that analyzes sensor data and manages MQTT communication.

---

## ⚙️ Working Logic

1.  **Security Active:** The security mode is turned on from the mobile application. The distance sensor verifies that the lid is closed.
2.  **Unauthorized Access:** When the lid is opened, the distance increases. The system detects this difference.
3.  **Alarm State:** Simultaneously, the Buzzer sounds, the LED flashes, and a "Safe Opened!" notification is sent to the phone over MQTT.
4.  **Deactivation:** When the user wants to open the lid, they first turn off the security from the mobile application, thereby accessing the safe without triggering the alarm.

---

## 🔓 License

This project is protected under the **MIT License**.
