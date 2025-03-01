# Robot-Please-Follow-The-Line-

Autonomous Line-Following Robot

An Arduino-based autonomous robot that follows a white line on a track using reflective sensors and PID controllers. The project integrates motor control, real-time feedback, and precise distance tracking, implemented in C++ and Arduino.

📌 Project Overview

This project involves designing and developing an autonomous robot that navigates a track using reflective sensors and a PID controller. The robot continuously adjusts its movement based on real-time feedback from the sensors, ensuring smooth and accurate path-following.

✨ Key Features

✔ PID Controller Implementation – Ensures smooth navigation✔ Real-time Distance Tracking – Accurate to three decimal places✔ Motor & Sensor Interface – Supports precise steering, stopping, and reversing✔ Custom PCB Design – Optimized for sensor performance✔ CAD Modeling – Structurally efficient robot design

🛠️ Hardware & Components

The robot consists of the following key components:

Microcontroller – Arduino (for processing and control)

Reflective Sensors – Detects track edges

Motors & Motor Drivers – Enables movement and steering

Custom PCB – Houses sensor circuits

Chassis & Mechanical Design – 3D-modeled structure for stability

🌟 Algorithm & Implementation

1️⃣ Distance Calculation Algorithm

Implemented in C++ (distancecalc.cpp) to track movement with high precision.Formula used:

Distance = (Encoder Count * Wheel Circumference) / Pulses per Revolution;

Ensures accurate tracking of movement, crucial for performance analysis.

2️⃣ PID Controller for Line Following

A Proportional-Integral-Derivative (PID) controller dynamically adjusts motor speeds based on sensor feedback.

PID Components:

Proportional (P) – Corrects based on how far the robot is from the center.

Integral (I) – Accumulates past errors to correct drift.

Derivative (D) – Predicts and smooths future movement.

PID Algorithm (Implemented in FinalCode - Group 37.cpp)

float Kp = 0.5, Ki = 0.02, Kd = 0.1;
float error = 0, prevError = 0, integral = 0;

void PIDControl() {
    error = calculateError();  // Compute deviation from track
    integral += error;
    float derivative = error - prevError;
    
    float correction = Kp * error + Ki * integral + Kd * derivative;
    
    adjustMotorSpeed(correction);
    
    prevError = error;
}

The PID function runs continuously, ensuring real-time course correction.

Optimized Kp, Ki, and Kd values for stability.

3️⃣ Motor & Sensor Integration

Developed motor control functions for speed adjustments, turning, and stopping.

Integrated sensor feedback to guide movement.

Code available in: Source Code/FinalCode - Group 37.cpp.

📁 Project Structure

📂 Autonomous-Robot-Project/
│── 📂 Source Code/
│   ├── distancecalc.cpp         # Distance calculation module
│   └── FinalCode .cpp           # Main control algorithm
│── 📂 Schematics/               # Stripboard circuit design
│── 📂 PCB/                      # Final PCB layout
│── 📂 Robot_CAD_Models/         # 3D models of the chassis
│── README.md                    # Project documentation

🛠️ Setup & Installation

🔹 Prerequisites

Ensure you have the following installed:

Arduino IDE (for compiling and uploading the code)

C++ Compiler (for distance calculation module)

🔹 How to Run the Project


Connect the Arduino board and upload the sketch.

Assemble the Hardware

Connect reflective sensors as per Schematics/ diagrams.

Mount the motors and PCB on the chassis.

Test & Calibrate

Run the robot on a track.

Tune Kp, Ki, Kd for optimized performance.

📊 Performance & Results

✅ Successfully follows a white line on various track shapes.✅ PID tuning significantly reduces oscillations.✅ Accurately calculates distance covered.

🚀 Future Improvements

🔹 Adaptive PID Control – Auto-tune Kp, Ki, and Kd values dynamically.🔹 Obstacle Detection – Add ultrasonic sensors for real-world applications.🔹 Power Optimization – Improve battery life and energy efficiency.

