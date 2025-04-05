# ⚙️ Motor Driver – L298N Overview

You can check the complete details about L298N on (Credits: https://www.st.com/resource/en/datasheet/l298.pdf)

## 🧠 What is a Motor Driver?

A **Motor Driver** bridges the gap between **low-power controllers** like an **Arduino UNO** and **high-power devices** like DC motors. The **L298N** motor driver is a dual H-Bridge driver that lets you **control the direction and speed of two DC motors** safely and efficiently. 💡🚗

---

## 🚗 Role in the DTMF-Controlled Robot Car

In this project, the **L298N driver** acts as the "power controller" 🔋. It takes **digital signals** from the **Arduino**, which is decoding tone commands via the DTMF module 🎵. Based on these signals, the L298N drives the motors to:

- 🔼 Move Forward  
- 🔽 Move Backward  
- ⬅️ Turn Left  
- ➡️ Turn Right  
- 🛑 Stop

Thanks to the L298N, our robot obeys commands (via phone) and motors respond with real-time motion! 🧠💪🔧

---

## 🌟 Key Features of L298N

| 🔧 Feature                  | 💬 Description |
|----------------------------|----------------|
| Dual H-Bridge              | Controls 2 DC motors independently |
| High Current Support       | Can handle **up to 2A per channel** |
| Wide Voltage Range         | Supports **5V to 35V** motor power |
| Direction Control          | Allows forward & reverse control |
| Speed Control              | PWM (Pulse Width Modulation) input for speed adjustment |
| Built-in Heat Sink         | Prevents overheating during long operations 🌡️ |
| Onboard 5V Regulator       | Powers your Arduino from the motor driver (if jumper is enabled) |
| Enable Pins                | Easily enable/disable individual motors |
| Compatible with MCU        | Works with Arduino, Raspberry Pi, ESP32 & others |

---

## 📐 Technical Specifications

| 📌 Specification             | 📊 Value |
|-----------------------------|----------|
| IC Model                    | L298N Dual H-Bridge |
| Motor Supply Voltage (Vms) | 5V to 35V |
| Logic Supply Voltage (Vss) | 5V |
| Max Output Current per Motor| 2A (continuous), 3A (peak) |
| Number of Channels          | 2 |
| Control Signal Level        | 5V logic compatible |
| Logic Inputs                | IN1, IN2, IN3, IN4 |
| Enable Pins                 | ENA (Motor A), ENB (Motor B) |
| Dimensions                  | ~43mm x 43mm x 27mm |
| Weight                      | ~26g |
| Onboard Regulator           | 78M05 (5V output from motor voltage) |
| Protection Features         | Heat sink, over-temp shutdown (IC level) |

---

## 🔌 Pin Description (Module Level)

| 🧲 Pin Name | 🎯 Function |
|------------|-------------|
| IN1, IN2   | Motor A direction control |
| IN3, IN4   | Motor B direction control |
| ENA        | PWM input for Motor A (speed control) |
| ENB        | PWM input for Motor B (speed control) |
| OUT1, OUT2 | Motor A terminals |
| OUT3, OUT4 | Motor B terminals |
| VCC        | Motor power supply (5V–35V) |
| 5V         | Logic power output/input (via jumper) |
| GND        | Common ground |
| Jumper Cap | If connected, enables 5V regulator output to logic power (for Arduino) |

---

## 💡 Usage in Robot Car

- 🎮 Controls **two motors** for all directions
- ⚡ Handles higher **motor current and voltage** than Arduino
- 🧯 Protects Arduino from back-EMF and overheating
- 🔄 Enables **PWM speed control** for smooth movement

---

## 🔋 Pro Tip

If you're **powering Arduino** from the **L298N's 5V output**, make sure your **motor voltage is at least 7V–12V**. Remove the **jumper cap** if you're powering Arduino separately!

---

