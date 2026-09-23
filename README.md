# Smart Home System with Security and Web Control

An ESP32-based smart home simulation developed as a microprocessor course project.  
The system combines home security, lighting control, temperature monitoring, motion detection, OLED displays, servo motors, keypad input, and Wi-Fi/web-based control.

## Overview

This project implements a smart home system with two main goals:

- Secure access control for the house
- Monitoring and controlling different home components

The system was developed and simulated using **ESP32** and **Wokwi**.

## Features

### 🔐 Smart Security System
- Password-based access using a 4×4 keypad
- Password status displayed on an OLED screen
- `#` confirms the password and `*` clears the input
- Two servo motors simulate opening and closing the entrance door
- Interior lights are activated after successful authentication
- Three consecutive incorrect passwords trigger a buzzer alarm
- The system enters a temporary security lockout after repeated failed attempts

### 💡 Intelligent Lighting
- Five LEDs simulate indoor lighting
- Manual lighting control using a push button
- LDR sensor measures ambient light
- Indoor LED brightness is adjusted according to the ambient light level
- Three LEDs simulate yard lighting

### 🌡️ Temperature Control
- DHT22 sensor measures the environment temperature
- A servo motor simulates the cooling fan
- The fan is activated when the temperature rises above 30°C
- Fan operation is divided into Low, Medium, and High temperature ranges
- Temperature and fan status are displayed on the OLED

### 🚶 Motion Detection and Yard Control
- PIR sensor detects movement in the yard
- Yard door is controlled using a servo motor
- Yard lights turn on when motion is detected
- The yard light can also be turned off manually
- The system reports yard events through the Serial Monitor

### 🖥️ OLED Monitoring and Menu
Two OLED displays are used:

- Security display for authentication and security messages
- Home-status display for monitoring the house

The home-status display can show:
- Door status
- LDR/light level
- Temperature
- Fan status
- PIR motion status

The project also includes an interactive keypad-based menu for:
- Home Status
- Light Control
- Fan Information
- Burglar Alarm

### 🌐 Wi-Fi and Web Interface
The project is designed to support Wi-Fi connectivity and a web-based smart-home interface.

The web interface includes:
- Password/login interface
- Smart-home dashboard
- Door control
- Indoor and yard light control
- Fan control
- Real-time system status

## Hardware

| Component | Purpose |
|---|---|
| ESP32 | Main microcontroller and Wi-Fi |
| OLED ×2 | Security messages and system monitoring |
| 4×4 Keypad | Password and menu input |
| DHT22 | Temperature measurement |
| LDR | Ambient light measurement |
| PIR Sensor | Motion detection |
| Servo ×4 | Entrance doors, fan, and yard door |
| Buzzer | Security alarm |
| LED ×5 | Indoor lighting |
| LED ×3 | Yard lighting |
| Push Buttons | Manual control of doors and lights |

## Software & Technologies

- **ESP32**
- **C/C++**
- **Arduino Framework**
- **FreeRTOS tasks on ESP32**
- **Wi-Fi**
- **Web Server**
- **Wokwi Simulator**
- Adafruit SSD1306
- Adafruit GFX
- DHT sensor library
- Keypad library
- ESP32Servo

## System Architecture

The project uses separate tasks for different parts of the smart-home system, including:

- Security control
- Indoor LED control
- Fan/temperature control
- Yard and motion control
- OLED home-status updates

This task-based design allows different components of the system to operate independently.

## Security Flow

```text
System Start
     │
     ▼
Security System Activated
     │
     ▼
Enter Password
     │
 ┌───┴────┐
 │        │
Correct   Wrong
 │        │
 ▼        ▼
Open     Increase
Door     Attempts
 │        │
 ▼        ▼
Lights   3 Failed Attempts
ON       │
 │       ▼
 ▼      Alarm
Close   / Lockout
Door
 │
 ▼
Security System Reactivated
```

## Wokwi Simulation

The project can be simulated online using Wokwi:

[Open the Wokwi Simulation](https://wokwi.com/projects/433567081351992321)

## Project Structure

A suggested GitHub repository structure is:

```text
Smart-Home-ESP32/
│
├── README.md
├── src/
│   └── sketch.ino
├── diagram.json
├── libraries.txt
└── report/
    └── project3.pdf
```

## Author

**Nazanin Niazi**

Computer Engineering  
Persian Gulf University

## Academic Project

Microprocessor Course — Project 3  
Summer 2025 (1404)
