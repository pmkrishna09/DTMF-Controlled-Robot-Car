# **🤖📱 DTMF-Controlled-Robot-Car 🚗🎯**
Project on buidling a Robot Car using Dual Tone Multi-Frequency For Surveillance

## 📄 Project Description & Overview
This project develops a **DTMF-based robotic vehicle** controlled remotely via **cell phone signals** for **rescue missions and surveillance applications**.
This project demonstrates a simple yet effective mobile robot that can be controlled remotely using **DTMF (Dual-Tone Multi-Frequency)** signals — the same tones generated when pressing keys on a mobile phone. It’s designed to interpret these tones via an audio-based DTMF decoder and use them to direct a robot car’s movement through an **Arduino-based control system**.  

The entire setup allows for **wireless, offline, real-time control** without needing internet or specialized RF modules.

This robot serves as a cost-effective solution for remote-controlled navigation, especially in environments where internet or RF remotes may not be feasible. 📞⚙️

---


## ⭐ Key Features & Functionality

- 📱 **Remote mobile phone control** (call and press keys)
- ✅ **Remote Access via Mobile Calls** – Control the robot from anywhere just by calling it and pressing the phone’s keypad.  
- 🔊 **DTMF decoding** using MT8870
- ✅ **DTMF Signal Decoding** – Converts keypad tones into digital instructions using the MT8870 DTMF decoder. 
- ⚡ **Real-time direction control** (forward, back, left, right, stop)
- ✅ **Real-Time Motion Control** – Responds instantly to commands like forward, backward, left, right, and stop.
- 🧠 **Arduino-based logic** (embedded C)
- ✅ **Simple Hardware Integration** – Uses low-cost components like Arduino, L293D, and a basic motor driver.
- ✅ **Hands-On Embedded Programming** – Offers solid practice with Arduino IDE and embedded C/C++. 
- 🚫 **No internet or Bluetooth needed**
- ✅ **No Internet Needed** – Operates fully offline via cellular communication. 
- 🧰 **Low-cost, easy-to-build system**


## 🧩 Technologies Used
- **Microcontroller:** Arduino UNO
- **Programming:** C, Python
- **Tools:** Proteus, Arduino IDE
- **DTMF:** Dual Tone Multi-Frequency


---

## 🧠 System Design & Implementation

## **🔸 Components Used:**  
- **Arduino UNO** – Brain of the robot for processing decoded inputs  
- **DTMF Decoder Module (MT8870)** – Converts audio tones from the mobile phone into digital signals  
- **Motor Driver IC (L293D)** – Drives the DC motors based on Arduino commands  
- **DC Motors & Chassis** – Enable mobility  
- **Mobile Phone & AUX Interface** – Used to receive input tones  

## **🔸 Working Principle:**  
1. A mobile phone is attached to the robot and kept in auto-answer mode.  
2. When the user calls the robot and presses keypad buttons (e.g., 2 for forward, 8 for backward), the audio tones are sent over the call.  
3. The MT8870 decodes these tones into 4-bit digital outputs.  
4. The Arduino reads these bits, maps them to motor control commands, and actuates the L293D driver accordingly.  
5. The robot then moves based on the command:  
   

### 🔸 Movement Mapping
| Key | Direction |
|-----|-----------|
| 2   | Forward   |
| 8   | Backward  |
| 4   | Left      |
| 6   | Right     |
| 5   | Stop      |


**🛠️ Software & Logic:**  
- Programmed using the **Arduino IDE**  
- Uses **conditional logic** (`if-else` statements) to map DTMF input codes to motor movements  
- Embedded programming in **C/C++** with modular code structure for easy upgrades

---

## 🚀 Applications

🔹 **Search & Rescue Missions** – Can reach remote or dangerous locations where human presence is risky.  
🔹 **Remote Surveillance** – Modified with cameras for security and monitoring.  
🔹 **Educational Demonstration** – Great for students learning embedded systems, signal processing, and robotics.  
🔹 **Defense Use-Cases** – Ideal for bomb disposal units or spy robots where RF or Wi-Fi is not suitable.  
🔹 **Disaster Management** – Can be used in collapsed buildings to search for survivors.  

---


<details>
<summary>📐Block Diagram</summary>

![DTMF Robot Block Diagram](path-to-your-image/dtmf-robot-block-diagram.png)


</details>

---

<details>
<summary>💻 Sample Code Snippet (Arduino)</summary>

```cpp
// DTMF Controlled Robot - Arduino Code
int motor1Pin1 = 2;
int motor1Pin2 = 3;
int motor2Pin1 = 4;
int motor2Pin2 = 5;
int dtmfPin1 = 6; // MSB
int dtmfPin2 = 7;
int dtmfPin3 = 8;
int dtmfPin4 = 9; // LSB

void setup() {
  pinMode(motor1Pin1, OUTPUT);
  pinMode(motor1Pin2, OUTPUT);
  pinMode(motor2Pin1, OUTPUT);
  pinMode(motor2Pin2, OUTPUT);

  pinMode(dtmfPin1, INPUT);
  pinMode(dtmfPin2, INPUT);
  pinMode(dtmfPin3, INPUT);
  pinMode(dtmfPin4, INPUT);
}

void loop() {
  int code = (digitalRead(dtmfPin1) << 3) |
             (digitalRead(dtmfPin2) << 2) |
             (digitalRead(dtmfPin3) << 1) |
             (digitalRead(dtmfPin4));

  switch (code) {
    case 0x02: moveForward(); break;  // Key '2'
    case 0x08: moveBackward(); break; // Key '8'
    case 0x04: turnLeft(); break;     // Key '4'
    case 0x06: turnRight(); break;    // Key '6'
    case 0x05: stopRobot(); break;    // Key '5'
  }
}

// Motor control functions go here...
