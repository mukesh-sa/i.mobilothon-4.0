# i.mobilothon-4.0
Round - II: Prototype Submissions


# Laser Attack Prevention for Car Cameras

This project implements a **two-stage method** to detect and prevent laser attacks on car cameras. Laser attacks can damage the video feed and the camera lens itself, rendering the system unusable. Our solution helps mitigate this by leveraging machine learning and frame analysis to detect potential laser threats in real time.

---

## Table of Contents
1. [Overview](#overview)
2. [Features](#features)
3. [Methodology](#methodology)
4. [Requirements](#requirements)
5. [Usage](#usage)
6. [Output](#output)

---

## Overview
Modern car cameras are susceptible to damage caused by laser attacks. These attacks can:
- Permanently damage the camera lens.
- Corrupt the video feed, causing blind spots for automated systems.

### **Proposed Solution**
A **two-stage detection system**:
1. **Stage 1**: A pre-trained machine learning model detects if the frame contains a laser attack.
2. **Stage 2**: Frame difference analysis validates the attack by comparing the current frame to the previous one. Significant changes indicate a potential laser attack.

By implementing this, we enhance both detection accuracy and reliability, minimizing false positives.

---

## Features
- **Real-Time Laser Attack Detection**: Processes every captured frame for quick decision-making.
- **Dual Validation**: Combines machine learning predictions with frame difference analysis.
- **Robustness**: Designed to prevent lens damage and maintain video feed quality.

---

## Methodology
1. **Frame Analysis via Pretrained Model**:
    - Each frame is processed by a pretrained model that classifies it as either:
      - **Normal**: No laser detected.
      - **Laser Attack**: Laser detected.

2. **Frame Difference Validation**:
    - The difference between the current and previous frames is calculated.
    - Large differences indicate a possible laser attack, confirming the model's prediction.

---

## Requirements
- Python 3.8+
- TensorFlow 2.x
- NumPy
- OpenCV
- Matplotlib

Install dependencies with:

```bash
pip install -r requirements.txt
```

---

## Usage
1. **Run the Detection System**:
    - Use the ML model to classify each frame:
      ```bash
      python codes/ML/laser_detection.py
      ```
    - Perform frame difference analysis:
      ```bash
      python codes/frame difference/frame_diff.py
      ```

2. **Results**:
    - Outputs are saved in the `Output` folder, including:
      - Classified images
      - Logs for detected laser attacks

---

## Output

### Sample Results:
Below are sample images from the **Output** folder, showcasing detected laser attacks and normal frames:

| **Laser Attack Detected**          | **Normal Frames**                 |
|------------------------------------|----------------------------------|
| ![Laser Attack](Output/output_attacked.png) | ![Normal Frame](Output/output_unattacked.png) |

---

## Contribution
Feel free to contribute by:
- Improving model accuracy
- Enhancing detection logic
- Adding support for other camera damage scenarios

---

## Acknowledgments
Special thanks to:
- **Team Volkswagen** for the oppurtunity.
- The open-source community for invaluable resources.
