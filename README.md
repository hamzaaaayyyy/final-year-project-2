# 🚗 Risk-Aware AI Navigation System

## Overview
This project is a **real-time AI Navigation and Collision Avoidance System** that uses computer vision and deep learning to detect objects, assess risk levels, and suggest navigation actions.

The system processes live webcam input, tracks moving objects, predicts potential collisions, and outputs safe navigation decisions such as **STOP, LEFT, or RIGHT**.

## Key Features
- Real-time object detection using YOLO
- Multi-object tracking with unique IDs
- Distance and speed estimation
- Risk scoring system (LOW, MEDIUM, HIGH)
- Collision prediction using motion analysis
- Smart avoidance actions:
  - STOP
  - LEFT
  - RIGHT
- Live visualization with bounding boxes and labels
- Optional video output recording

## Technologies Used
- Python
- OpenCV
- NumPy
- Ultralytics YOLO (Deep Learning Model)

## How It Works
1. Webcam captures live video feed.
2. YOLO model detects objects (person, car, bicycle, motorcycle).
3. Each object is tracked across frames.
4. System calculates:
   - Distance (based on bounding box size)
   - Speed (based on movement)
   - Position relative to center
5. A **risk score** is computed using:
   - Object priority
   - Distance
   - Speed
   - Position
6. Collision is predicted using trajectory analysis.
7. Navigation action is generated:
   - HIGH risk → STOP
   - MEDIUM/LOW risk → LEFT or RIGHT

## Important Classes Detected
- Person
- Car
- Bicycle
- Motorcycle

## Risk Levels
| Score Range | Risk Level |
|------------|-----------|
| > 0.75     | HIGH      |
| 0.4 - 0.75 | MEDIUM    |
| < 0.4      | LOW       |

## Project Structure
```bash
AI-Navigation/
│── main.py              # Main execution file
│── output.mp4           # Saved output video (optional)
│── README.md            # Documentation
