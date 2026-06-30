# 🧠 Indian Sign Language Recognition System

![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-Deep%20Learning-orange?logo=tensorflow)
![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-green?logo=opencv)
![MediaPipe](https://img.shields.io/badge/MediaPipe-Hand%20Tracking-red)
![Node.js](https://img.shields.io/badge/Node.js-Backend-success?logo=node.js)
![Express.js](https://img.shields.io/badge/Express.js-API-black?logo=express)
![License](https://img.shields.io/badge/License-Educational-lightgrey)

A real-time **Indian Sign Language Recognition System** developed as a **B.Tech Computer Science Min Project** at **Mangalam College of Engineering**.

The project utilizes **MediaPipe**, **TensorFlow**, and **OpenCV** to detect hand gestures representing **Indian Sign Language alphabets (A–Z)** and **numbers (1–9)**. The recognized gesture is transmitted in real time to an **Express.js backend**, where it is stored and made available through a REST API.

---

# 📑 Table of Contents

- Overview
- Features
- Project Structure
- Technology Stack
- Installation
- Usage
- Dataset
- REST API
- Demo
- Contributors
- License

---

# 📖 Overview

Communication can be challenging for individuals who rely on sign language. This project bridges that gap by recognizing hand gestures through a webcam and converting them into text in real time.

The application performs the following steps:

- Detects hands using **MediaPipe Hands**
- Extracts 21 hand landmarks
- Normalizes landmark coordinates
- Predicts the corresponding sign using a trained TensorFlow model
- Displays the prediction on screen
- Sends the prediction to an Express.js backend
- Stores the latest detected character for external applications

---

# ✨ Features

- ✅ Real-time webcam-based sign language recognition
- ✋ Hand landmark detection using MediaPipe
- 🧠 TensorFlow/Keras classification model
- 🔤 Supports alphabets **A–Z**
- 🔢 Supports numbers **1–9**
- 📡 Sends predictions to an Express.js backend
- 📸 Automatically saves the latest prediction image
- ⚡ Lightweight and fast inference
- 🌐 REST API for accessing predictions

---

# 📂 Project Structure

```
CSE_MinProject/
│
├── sign_dataset/
│   └── landmarks_from_images.csv
│
├── server/
│   ├── index.js
│   ├── package.json
│   └── node_modules/
│
├── landmarks_from_images.h5
├── main.py
├── o.jpg
├── requirements.txt
└── README.md
```

---

# 🛠 Technology Stack

## Machine Learning

- Python
- TensorFlow / Keras
- OpenCV
- MediaPipe
- NumPy
- Pandas

## Backend

- Node.js
- Express.js
- Body-parser
- CORS

---

# 🚀 Installation

## 1. Clone the Repository

```bash
git clone https://github.com/rahulrajancc/CSE_MinProject.git

cd CSE_MinProject
```

---

## 2. Install Python Dependencies

```bash
pip install -r requirements.txt
```

or

```bash
pip install opencv-python mediapipe tensorflow pandas numpy requests
```

### Optional (Virtual Environment)

Linux/macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

Windows

```bash
venv\Scripts\activate
```

Then install dependencies

```bash
pip install -r requirements.txt
```

---

## 3. Install Node.js Dependencies

```bash
cd server

npm install
```

---

# ▶️ Usage

## Start the Backend

```bash
cd server

node index.js
```

The Express server will start on

```
http://localhost:7000
```

---

## Run the Recognition System

```bash
python main.py
```

The webcam will open automatically.

Show a hand gesture representing an alphabet or number.

The system will

- Detect the hand
- Predict the sign
- Display it on screen
- Save the latest image
- Send the prediction to the backend

Press **Esc** to exit.

---

# 📊 Dataset

The model is trained using a CSV dataset containing normalized hand landmarks extracted from gesture images.

Example:

```python
import pandas as pd

df = pd.read_csv("sign_dataset/landmarks_from_images.csv")

print(df.shape)

print(df.head())
```

Dataset Format

- 1 Label Column
- 63 Landmark Features

---

# 🌐 REST API

## POST /predict

Stores the latest prediction.

Request

```json
{
  "prediction": "A",
  "image": "o.jpg"
}
```

---

## GET /latest

Returns the most recent prediction.

Response

```json
{
  "latestPrediction": "A"
}
```

---

# 🧪 Demo

Workflow

```
Webcam
      │
      ▼
MediaPipe Hand Detection
      │
      ▼
Landmark Extraction
      │
      ▼
TensorFlow Prediction
      │
      ▼
Display Character
      │
      ▼
Express.js API
      │
      ▼
Latest Prediction
```

Visit

```
http://localhost:7000/latest
```

to view the most recent prediction.

---

# 👨‍💻 Contributors

**Mangalam College of Engineering**

B.Tech Computer Science & Engineering

- Rahul Rajan
- Shoan Kurien Johnson
- Sohil Suman
- Shijin Varghese

---

# 🎓 Academic Information

**Project Title**

Indian Sign Language Recognition System

**Course**

B.Tech Computer Science & Engineering

**Institution**

Mangalam College of Engineering

---

# 📜 License

This project was developed for **educational purposes** as part of the **B.Tech Computer Science Engineering Min Project**.

Feel free to use it for learning and academic reference.

---

## ⭐ Support

If you found this project helpful, consider giving the repository a ⭐ on GitHub.

It helps others discover the project and supports future development.
