
# 🚗 Bluetooth Controlled Robot Car

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white" />
  <img src="https://img.shields.io/badge/Language-C++-blue?style=for-the-badge&logo=cplusplus" />
  <img src="https://img.shields.io/badge/Control-Bluetooth-blueviolet?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge" />
</p>

<p align="center">
  <i>Control your robot car wirelessly using Bluetooth and Arduino!</i>
</p>

---

## ✨ About The Project

The **Bluetooth Controlled Robot Car** is an Arduino-based robotics project that allows users to control a robot car wirelessly using Bluetooth communication.

The Arduino receives commands from a smartphone and controls the motors through a motor driver to move the robot in different directions.

## 🌟 Features

- ⬆️ Forward Movement
- ⬇️ Backward Movement
- ⬅️ Left Turn
- ➡️ Right Turn
- 🛑 Stop Function
- 📡 Wireless Bluetooth Control
- ⚡ Arduino-Based Motor Control

## 🛠️ Components Required

| Component | Quantity |
|---|---|
| Arduino UNO | 1 |
| L298N Motor Driver | 1 |
| DC Motors | 4 |
| Bluetooth Module (HC-05/HC-06) | 1 |
| Robot Car Chassis | 1 |
| Battery | 1 |
| Jumper Wires | As required |

## 🔌 Pin Configuration

| Arduino Pin | Motor Driver |
|---|---|
| D5 | IN1 |
| D6 | IN2 |
| D9 | IN3 |
| D10 | IN4 |

## 🎮 Control Commands

| Command | Function |
|:---:|---|
| `F` | ⬆️ Forward |
| `B` | ⬇️ Backward |
| `L` | ⬅️ Left |
| `R` | ➡️ Right |
| `S` | 🛑 Stop |

## 💻 Arduino Source Code

```cpp
char command;

int IN1 = 5;
int IN2 = 6;
int IN3 = 9;
int IN4 = 10;

void setup() {
  Serial.begin(9600);

  pinMode(IN1, OUTPUT);
  pinMode(IN2, OUTPUT);
  pinMode(IN3, OUTPUT);
  pinMode(IN4, OUTPUT);
}

void loop() {
  if (Serial.available() > 0) {
    command = Serial.read();

    switch (command) {

      case 'F': // Forward
        digitalWrite(IN1, HIGH);
        digitalWrite(IN2, LOW);
        digitalWrite(IN3, HIGH);
        digitalWrite(IN4, LOW);
        break;

      case 'B': // Backward
        digitalWrite(IN1, LOW);
        digitalWrite(IN2, HIGH);
        digitalWrite(IN3, LOW);
        digitalWrite(IN4, HIGH);
        break;

      case 'L': // Left
        digitalWrite(IN1, LOW);
        digitalWrite(IN2, HIGH);
        digitalWrite(IN3, HIGH);
        digitalWrite(IN4, LOW);
        break;

      case 'R': // Right
        digitalWrite(IN1, HIGH);
        digitalWrite(IN2, LOW);
        digitalWrite(IN3, LOW);
        digitalWrite(IN4, HIGH);
        break;

      case 'S': // Stop
        digitalWrite(IN1, LOW);
        digitalWrite(IN2, LOW);
        digitalWrite(IN3, LOW);
        digitalWrite(IN4, LOW);
        break;
    }
  }
}
```

## ⚙️ Working Principle

1. The smartphone sends commands through Bluetooth.
2. The Bluetooth module receives the commands.
3. Arduino reads the commands using Serial Communication.
4. The `switch` statement identifies the received command.
5. Arduino sends signals to the motor driver.
6. The motors rotate according to the selected direction.

## 🚀 Installation & Setup

1. Assemble the robot car chassis.
2. Connect the motors to the motor driver.
3. Connect the motor driver to Arduino.
4. Connect the Bluetooth module.
5. Upload the Arduino code.
6. Pair your smartphone with the Bluetooth module.
7. Open a Bluetooth controller application.
8. Send commands to control your robot car.

## 🔮 Future Improvements

- 📱 Custom Android Application
- 🎚️ Motor Speed Control
- 🚧 Obstacle Avoidance
- 📷 Wireless Camera
- 🤖 Autonomous Navigation

---

## 👨‍💻 Author

### Sumit Yadav

**Interests:** Arduino | Robotics | Electronics | Embedded Systems

---

<p align="center">
  ⭐ If you like this project, don't forget to give it a star!
</p>

<p align="center">
  <b>Made with ❤️ by Sumit Yadav</b>
</p>
