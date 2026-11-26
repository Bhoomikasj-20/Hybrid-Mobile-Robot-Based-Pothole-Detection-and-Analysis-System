<p align="center">
  <strong>Hybrid Mobile-Robot Based Pothole Detection and Analysis System.</strong>
</p>

📌 Project Overview

Road potholes are a major concern for road safety, vehicle maintenance, and transportation infrastructure. Traditional road inspection methods often require manual surveys, which can be time-consuming and labor-intensive.

This project presents an ESP32-based mobile robotic vehicle that integrates remote-controlled mobility, GPS tracking, live video streaming, AI-based pothole detection, and Telegram notifications.

The robot captures live road footage using an ESP32-CAM module. The video stream is processed on a laptop using a YOLOv11-based pothole detection model with OpenCV. When a pothole is detected, its approximate size is estimated using pixel measurements, and an alert is sent through a Telegram bot. The NEO-6M GPS module provides geographical coordinates for location tracking.

The project demonstrates the integration of embedded systems, robotics, computer vision, GPS technology, and IoT-based communication in a single platform.

🎯 Project Objectives

Develop a four-wheel mobile robot using ESP32 and BO motors.

Enable wireless manual robot control through Bluetooth.

Integrate GPS tracking using the NEO-6M GPS module.

Stream live video using the ESP32-CAM module.

Detect potholes from the live video stream using YOLOv11.

Estimate pothole dimensions using pixel-based measurements.

Send real-time pothole detection notifications through Telegram.

Demonstrate an affordable solution for mobile road inspection.

🤖 Hardware Implementation

The robotic platform consists of the following components:

Component

Purpose

ESP32 Development Board

Robot motion control and GPS data handling

ESP32-CAM

Live video capture and Wi-Fi streaming

L298N Motor Driver

Controls the DC motors

4 × BO Motors (100 RPM)

Four-wheel robot mobility

NEO-6M GPS Module

Geographical coordinate tracking

2-Cell Li-ion Battery

Power supply

Robot Chassis and Wheels

Mechanical structure

Hardware Setup

Add actual photographs of your assembled robot and individual hardware components here.



Figure 1: Complete robotic vehicle
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/a6592f89-e5d3-4159-8869-3ee928931d23" />



🛠️ Technology Stack

Embedded Systems

ESP32

ESP32-CAM

Arduino IDE

Bluetooth communication

GPS integration

Computer Vision and AI

Python

YOLOv11

OpenCV

Ultralytics

Communication and Notifications

Wi-Fi video streaming

Telegram Bot API

Serial Bluetooth Terminal (Android)

Development Environment

PyCharm

Google Colab (optional for model training)

🏗️ System Architecture

The system uses two ESP32 boards to perform separate functions.

Robot Control and GPS: The primary ESP32 controls the four BO motors through the L298N motor driver. It receives manual movement commands from a smartphone through built-in Bluetooth and retrieves GPS coordinates from the NEO-6M module.

Live Video Streaming: The ESP32-CAM captures road footage and streams live video over Wi-Fi to a laptop.

Pothole Detection: The laptop receives the video stream, and the YOLOv11 model processes the frames to identify potholes.

Size Estimation: The detected pothole's bounding-box pixel measurements are used to estimate its approximate dimensions using a calibration factor.

Telegram Notification: When a pothole is detected above the configured confidence threshold, the system sends a notification through the Telegram Bot API.

System Architecture Diagram
<img width="1600" height="1118" alt="image" src="https://github.com/user-attachments/assets/5bd723b5-7690-4681-b04f-efa156a4ac4a" />

⚙️ Working Methodology

Step 1: Robot Mobility and Control

The robot uses four 100 RPM BO motors connected through an L298N motor driver. Movement is controlled manually using Bluetooth communication between the ESP32 and a smartphone.

Supported movements:

Forward

Backward

Left

Right

Stop

Step 2: GPS Tracking

The NEO-6M GPS module retrieves geographical coordinates. The ESP32 processes the GPS information and transmits the coordinates to the Serial Bluetooth Terminal application.

Step 3: Live Video Streaming

The ESP32-CAM captures road footage and streams it over Wi-Fi to a laptop for real-time visual processing.

Step 4: AI-Based Pothole Detection

The laptop processes incoming video frames using OpenCV and the YOLOv11 pothole detection model. The model identifies potholes and generates bounding boxes around detected regions.

Step 5: Pothole Size Estimation

The dimensions of the detected bounding boxes are measured in pixels. A calibration factor is used to estimate approximate real-world pothole dimensions.

Step 6: Telegram Alert

When the detection satisfies the configured confidence threshold, a Telegram bot sends an alert containing detection information and a timestamp. GPS coordinates can also be included in the notification when integrated into the alert workflow.

📍 GPS Tracking

The NEO-6M GPS module is used to obtain the robot's geographical location.

Information handled:

Latitude

Longitude

Optional altitude, speed and time

GPS coordinates are transmitted to the smartphone through the ESP32's built-in Bluetooth and displayed in the Serial Bluetooth Terminal application.

📷 Dataset

This repository provides sample pothole images and related documentation to demonstrate the visual data used in the project.

Dataset information:

Dataset type: Pothole image dataset
