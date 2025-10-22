---
layout: post
title: CrashAlert
description:  CrashAlert is an innovative safety device designed to automatically contact first responders in the event of a car accident. The system eliminates the need for the victim to call for help by instantly transmitting an emergency alert once a crash is detected. Equipped with a built-in GPS module, CrashAlert accurately pinpoints the location of the incident, ensuring that responders can reach the scene as quickly as possible. The device also features an independent battery system to maintain reliable operation even if the vehicle’s power supply is disrupted. This project integrates of sensors, AVR microcontroller, and GPS communication to enhance road safety and emergency response efficiency.

skills: 
  - Baremetal AVR
  - PCB design
  - Circuit design
  - Soldering

main-image: /main.png
---



---
#  Crash Detection & Alert System (Arduino + SIM800L + GPS NEO-6M + MPU6050)

This project implements a crash detection and emergency alert system using AVR microcontroller.  
It measures sudden acceleration changes using an MPU6050 accelerometer, retrieves location data from a GPS module (NEO-6M), and sends an SMS alert with a Google Maps link via the SIM800L GSM module.

---

## responsibilities
- Developed a crash detection device using Arduino Nano, MPU6050 IMU, GPS NEO-6M, and SIM800L GSM module.
- Implemented real-time accident detection algorithms based on accelerometer and gyroscope data.
- Integrated GPS to capture location coordinates during an accident event.
- Programmed GSM module to automatically send SMS alerts with live location to emergency contacts.
- Designed the hardware system with buzzer and LED for user feedback and status indication.
- Conducted testing and calibration to ensure reliable detection and minimal false positives.
---

##  Hardware 

- **MPU6050** – 3-axis accelerometer (accessed via I²C registers)
- **NEO-6M GPS Module**
- **SIM800L GSM Module**
- **Buzzer** (on pin D11)
- **Status LED** (RED LED)
- **Push button** (connected to D2, external interrupt reset)


---

##  How It Works

1. **Crash Detection (MPU6050)**  
   - MPU6050 is initialized over I²C.  
   - Raw accelerometer data is read from registers (`0x3B–0x40`).  
   - Acceleration differences (`ΔX, ΔY, ΔZ`) are computed frame-to-frame.  
   - If the magnitude exceeds the acceleration threshold (`aThreshold = 5 m/s²`) for more than `tThreshold = 500 ms`, a crash is assumed.

2. **GPS Location (NEO-6M + TinyGPS++)**  
   - GPS bytes are parsed in real time using `TinyGPS++`.  
   - Updates latitude, longitude, and time.  
   - If no valid fix is available for 5+ seconds, `gpsConnected` is set to false.

3. **SMS Alert (SIM800L)**  
   - If a crash is detected, SIM800L sends an SMS.  
   - Message contains timestamp and Google Maps link:  
     ```
     Crash Detected! time: HH:MM:SS 
     Location: https://www.google.com/maps/search/?api=1&query=<lat>,<lon>
     ```
   - If GPS fix is not available, fallback message is sent.

4. **Indicators**  
   - **Buzzer (pin 11)** activates continuously after crash detection.  
   - **LED (pin 13)** lights up during crash alert.  
   - **Push button (pin 2)** clears crash state via external interrupt.

---




