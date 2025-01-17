# Touch Processing Application with Gesture Recognition

## Overview

The **Touch Processing Application** is a gesture-based control system that recognizes predefined touch gestures to automate tasks on both mobile and laptop platforms. By leveraging Convolutional Neural Networks (CNNs) and a pre-trained ResNet-18 model, the application provides seamless interaction between users and their devices using gestures like "L," "S," and "Star."

This project demonstrates how gestures can be used to perform actions such as opening applications, taking screenshots, or opening multiple applications simultaneously, making it a powerful tool for enhancing user interaction.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Usage](#usage)
- [Model Details](#model-details)
- [Results](#results)
- [Challenges](#challenges)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)
- [Project Demonstration](#project-demonstration)

## Introduction

This project aims to implement a gesture recognition system using Convolutional Neural Networks (CNNs) for mobile and laptop platforms. It processes touch data from the mobile app and cursor movements from the laptop to recognize predefined gestures, which are mapped to various actions like opening applications, taking screenshots, or launching multiple apps simultaneously. 

The core functionality of the system leverages a pre-trained **ResNet-18** model from the PyTorch library to classify gestures based on images captured from the device’s camera or the laptop’s cursor movements.

## Features

- **Gesture Recognition:** Recognizes "L," "S," and "Star" gestures.
- **Cross-Platform Support:** Works on both mobile (Android) and laptop (Windows).
- **Automation:** Automates tasks like opening apps (e.g., Notepad, Calculator), taking screenshots, or opening multiple applications.
- **Mobile Gestures:** On mobile, it opens important photos (e.g., Aadhar card).
- **Real-Time Performance:** Low-latency recognition for efficient task execution.

## Technologies Used

- **Python**: Main language for backend logic and model training.
- **PyTorch**: Framework used for building and training the CNN model (ResNet-18).
- **Flask**: Backend framework for handling the communication between the mobile app and laptop.
- **Android Studio**: Used to develop the mobile application for touch gesture capture.
- **OpenCV**: Image processing library to work with touch images.
- **PyAutoGUI**: Used for automating actions like opening applications or taking screenshots.
- **Torchvision**: For image preprocessing and data augmentation during model training.

## Installation

### Clone the repository

```bash
git clone https://github.com/yourusername/touch-processing-application.git
cd touch-processing-application
```

### Set up the virtual environment

```bash
python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
```

### Install dependencies

```bash
pip install -r requirements.txt
```

### Set up the Flask backend

The Flask backend will communicate with the mobile app and the laptop.

1. Install Flask:

```bash
pip install Flask
```

2. Run the Flask server:

```bash
python app.py
```

### Set up the Android application

1. Open the Android Studio project located in the `android/` folder.
2. Build and run the application on your device or emulator.

## Usage

### Gesture Recognition on Laptop

1. **Start the Gesture Recognition**: The laptop application captures cursor movements and sends them to the Flask backend for gesture recognition.
2. **Perform Gestures**: You can perform gestures like "L," "S," and "Star" with the mouse to trigger various tasks.
   - **L**: Opens Calculator.
   - **S**: Takes a screenshot.
   - **Star**: Opens multiple applications (e.g., YouTube, Notepad, Calculator).

### Gesture Recognition on Mobile

1. **Install the Mobile App**: After building the Android app, install it on your mobile device.
2. **Perform Gestures**: Touch gestures on the screen, such as "L," "S," or "Star," trigger corresponding actions like opening important photos (e.g., Aadhar card).

## Model Details

- **Model**: ResNet-18 (Pre-trained on ImageNet)
- **Framework**: PyTorch
- **Libraries**: NumPy, Torchvision, Matplotlib
- **Training Process**:
   - The model was trained on a custom dataset consisting of images of gestures like "L," "S," and "Star."
   - Data augmentation techniques (e.g., random rotations, flips) were applied to improve the model's generalization ability.
   - The model was fine-tuned using the PyTorch `models.ResNet18_Weights.DEFAULT` pretrained weights from ImageNet.

### Key Metrics

- **Accuracy**: 95%
- **Precision**: 93%
- **Recall**: 92%
- **F1-score**: 92%

## Results

- **Laptop:**
  - **L Gesture**: Opens Calculator.
  - **S Gesture**: Takes a screenshot.
  - **Star Gesture**: Opens multiple applications (e.g., YouTube, Notepad, Calculator).

- **Mobile:**
  - **L Gesture**: Opens important photos like Aadhar card.

The model showed high accuracy in recognizing these gestures, with an overall performance improvement due to data augmentation.

## Challenges

- **Gesture Variability**: Different users perform gestures in various ways, which can lead to recognition errors. Data augmentation and model tuning helped mitigate this.
- **Real-time Performance**: Ensuring real-time recognition on mobile and laptop platforms posed a challenge. Optimizations were made to improve response time.
- **Device Synchronization**: Ensuring smooth communication between mobile and laptop devices was another challenge. This was addressed with efficient data handling via Flask.

## Future Work

- **Incremental Learning**: Implementing incremental learning would allow the model to learn new gestures dynamically without retraining from scratch.
- **Advanced Gesture Recognition**: Supporting more complex gestures like pinching, dragging, and multi-finger gestures.
- **Cross-Device Improvements**: Optimizing communication and performance between mobile and laptop devices.
- **User Personalization**: Allowing users to define their own gestures for personalized control.

## Contributing

1. Fork the repository.
2. Create a new branch (`git checkout -b feature-branch`).
3. Commit your changes (`git commit -am 'Add new feature'`).
4. Push to the branch (`git push origin feature-branch`).
5. Create a new Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Project Demonstration

For a detailed explanation and demonstration of how the application works, please watch the video below:

[Project Explanation and Demonstration](https://youtu.be/UpU0Mt5j5ic)
