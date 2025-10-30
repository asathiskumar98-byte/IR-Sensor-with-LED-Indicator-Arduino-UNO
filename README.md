# 👁️ IR Sensor with LED Indicator – Arduino UNO

A beginner-friendly project to detect the presence of an object using an **IR (Infrared) Sensor** and display the result through an **LED**.  
When an object is detected, the LED turns **ON** — a fundamental concept in obstacle detection and automation systems.

---

## 🧠 Overview

This project teaches:
- How to **interface an IR sensor** with Arduino UNO  
- How to read **digital sensor output**  
- How to trigger an **LED indicator** based on sensor input  

---

## ⚙️ Hardware Requirements

- Arduino UNO  
- IR Sensor Module  
- LED  
- 220Ω resistor  
- Breadboard and jumper wires  

---

## 🔌 Circuit Connections

| Component | Arduino Pin | Description |
|------------|--------------|--------------|
| IR Sensor OUT | D8 | Sensor output signal |
| LED | D7 | Indicator output |
| IR Sensor VCC | 5V | Power supply |
| IR Sensor GND | GND | Common ground |
| LED GND | GND (through 220Ω resistor) | Current limiting |

🧩 **Logic:**  
- When **no object** is detected → Sensor output is **HIGH** → LED **OFF**  
- When **object detected** → Sensor output is **LOW** → LED **ON**

---

## 💻 Arduino Code

```cpp
const int led = 7;
const int IR_sensor = 8;

void setup()
{
  pinMode(led, OUTPUT);
  pinMode(IR_sensor, INPUT); 
}

unsigned char sensor_state = 0;

void loop()
{
  sensor_state = digitalRead(IR_sensor);

  if(sensor_state == HIGH)
  {
    digitalWrite(led, LOW);  // No object detected
  }
  else
  {
    digitalWrite(led, HIGH); // Object detected
  }
}
```
🚀 How It Works
The IR sensor continuously emits infrared light.

When an object reflects this light back, the sensor outputs LOW.

The Arduino detects this change and turns ON the LED.

When no object is in range, the sensor output is HIGH, and the LED remains OFF.

📸 Output Behavior
Object Presence	IR Sensor Output	LED State
Object Detected	LOW	ON
No Object	HIGH	OFF

🧰 Software Tools
Arduino IDE (v2.0 or later)

Arduino UNO Board Drivers

💡 Applications
Line Following Robots

Automatic Door Systems

Obstacle Detection

Object Counter Projects
