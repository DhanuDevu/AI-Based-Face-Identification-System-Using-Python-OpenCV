🎭 Face Detection & Recognition System Using OpenCV & LBPH

This project implements a complete real-time face detection and recognition system using Python, OpenCV, Haarcascade, and the LBPH (Local Binary Pattern Histogram) algorithm.
It includes dataset creation, model training, and live face recognition using webcam input.

🚀 Features

Real-time face detection using Haarcascade

LBPH face recognition

Automatic dataset generation (100+ images per user)

Training script that creates trainer.yml and names.csv

Live recognition with name display

Fully offline – no internet needed

🧩 Project Workflow
1️⃣ Dataset Creation — face_datasets.py

Captures face images from webcam

Detects faces using Haarcascade

Saves images in dataset/<name>.<id>.<count>.jpg

Uses: haarcascade_frontalface_default.xml


face_datasets

2️⃣ Training the Model — training.py

Loads all face images from dataset/

Extracts IDs from filenames

Trains LBPH face recognizer

Saves trained model to trainer/trainer.yml

Creates names.csv containing ID–Name pairs


training

3️⃣ Real-Time Recognition — face_recognition.py

Loads the trained LBPH model

Uses Haarcascade to detect faces

Predicts ID + confidence

Looks up the name using names.csv

Displays name above the detected face


face_recognition

📂 Project Structure
project/
│── face_datasets.py
│── training.py
│── face_recognition.py
│── haarcascade_frontalface_default.xml
│── names.csv
│── dataset/              # Auto-generated face images
│── trainer/
│     └── trainer.yml     # Trained recognition model

🧠 How the System Works
Face Detection

Uses Haarcascade XML to locate faces in video frames.


haarcascade_frontalface_default

Face Recognition

LBPH extracts texture patterns and compares them with the trained model.

Name Mapping

names.csv links numeric IDs with real names of users.

🔧 How to Run
1. Create Dataset
python face_datasets.py


Look at the camera → program captures 100 images → press q to stop.

2. Train the Model
python training.py

3. Run Face Recognition
python face_recognition.py

📘 Requirements

Python 3

OpenCV (pip install opencv-python opencv-contrib-python)

NumPy

pandas

Pillow
