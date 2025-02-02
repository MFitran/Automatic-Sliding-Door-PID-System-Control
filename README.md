# Automatic Sliding Door PID System Control

This project is an Arduino based automatic sliding door control system. This system utilizes the VL53L0X sensor to detect the door, the HC-SR04 ultrasonic sensor to detect the position of an object, and a servo motor to move the door. Door movement control is carried out using the PID (Proportional-Integral-Derivative) algorithm.

## Feature
- Control sliding doors automatically based on the presence of objects.
- PID algorithm is used to ensure smooth and precise door movement.
- Equipped with a mechanism to open and close the door with high accuracy.

## Components Used
- **Arduino Uno**: As the main microcontroller.
- **VL53L0X**: Time-of-flight based distance measurement sensor.
- **HC-SR04**: Ultrasonic sensor to detect the presence of objects.
- **Servo Motor**: To move the door.
- **Supporting Components**: Jumper cables, breadboard and power supply.

## Ways of working
1. **Object Detection**  
   The HC-SR04 sensor detects the distance of objects on the front door. If the object distance is less than 115 mm, the door will open; otherwise, the door will close.
   
2. **Door Control**  
   VL53L0X is used to read door position in real-time. This value is compared with the setpoint (target position) using the PID algorithm, which calculates the output to control the servo motor.

3. **PID Setup**  
   PID constants are used to control system response. The constants used can be tuned in lines **49-51** in the code:  
   ```cpp
   float kp = 0.8;   // Proportional constant
   float ki = 0.015; // Integral constant
   float kd = 0.6;   // Derived constants
