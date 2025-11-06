---
layout: post
title: black dragon
description:   an ESP32 based board for rover type robots with built in BLE and WIFI connectivity.
    This board is intended for uses on robots with mechanum wheels with built in motor drivers and powered by a 2S - 4s lipo batteries.This board has been used in several projects that involves mechanum wheels i.e. the surveilance bot with built in camera module.

skills: 
  - PCB design
  - Circuit design
  - ESP32 microcontroller
  - Soldering
  


main-image: /BlackDragon.png
---

---
##  Schematic 
{% include image-gallery.html images="Schematic.jpg" height="400" %}

The schematic shown above represents the ESP32 BlackDragon Board, a custom-designed control system that integrates power management, motor control, and programming interfaces into a single compact platform. The core of the board is the ESP32 microcontroller, a high-performance, dual-core processor that manages all primary operations, including motor actuation, signal processing, and data communication.

This board is engineered to efficiently control multiple DC motors, enabling precise movement and direction control for robotics or automation projects. The ESP32 communicates directly with dedicated motor driver circuits, ensuring stable current delivery and smooth motor performance.

In addition to motor control, the BlackDragon board integrates a robust power regulation system, capable of accepting wide range of battery voltages. It employs step down and voltage regulators to provide consistent 3.3V and 5V power rails, providing the ESP32 and other components with apropiate voltages.

The design includes a USB-to-serial programmer interface, allowing direct communication between the ESP32 and a host computer for firmware upload and serial monitoring. The modular pin configuration provides flexibility for connecting external sensors, actuators, or additional peripherals, making the board versatile for various embedded applications.


---

##  PCB 
{% include image-gallery.html images="PCB.png" height="400" %}

- **custom esp32 board** 
- **3s lipo battery**
- **esp32-cam**
- **motor drivers** 
- **motors** 
- **mechanum wheels** 


---

