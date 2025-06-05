# 3D-Solar-Tracker

Video link https://youtu.be/W2714TZNUrw?si=tWTv5UUbsV33UBtd


# Arduino Solar Tracker

A dual-axis solar tracker using an Arduino and four Light Dependent Resistors (LDRs) to adjust the position of a solar panel or sensor in real-time for optimal sunlight exposure.

## 🛠️ Features

- Dual-axis control using servo motors
- Real-time light intensity sensing with LDRs
- Adjustable tolerance and servo movement limits
- Automatic alignment with the brightest light source

## 📦 Components Used

- Arduino Uno (or compatible board)
- 2x Servo Motors (horizontal and vertical control)
- 4x LDRs (Light Dependent Resistors)
- 4x 10kΩ resistors (for LDR voltage dividers)
- Breadboard and jumper wires
- External power supply (if required for servos)

## ⚙️ Pin Configuration

| Component         | Arduino Pin |
|------------------|-------------|
| Horizontal Servo  | D9          |
| Vertical Servo    | D10         |
| LDR Top-Left      | A0          |
| LDR Bottom-Left   | A1          |
| LDR Top-Right     | A2 *(fix suggested)* |
| LDR Bottom-Right  | A3          |

> ⚠️ **Note**: The original code uses `A3` for both top-right and bottom-right LDRs. It’s recommended to assign `A2` to the top-right LDR for correct operation.

## 🚀 Getting Started

1. Connect the LDRs in a voltage divider configuration with 10kΩ resistors.
2. Connect servos to digital pins and provide sufficient power.
3. Upload the code to your Arduino using the Arduino IDE.
4. Place the setup in a light-sensitive area and watch it track the strongest light source.

## 🧠 How It Works

- The four LDRs are placed in a cross formation.
- The code calculates average light intensity from each direction.
- Differences between top-bottom and left-right light values determine the motion.
- Servo motors adjust angles gradually to align with the brightest source.

## 📁 Code Structure

```cpp
Servo horizontal, vertical;
analogRead(A0-A3);  // LDR inputs
horizontal.write(); // Move horizontal servo
vertical.write();   // Move vertical servo
