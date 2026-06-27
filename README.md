# ASL Hand Gesture Recognition System

A real-time **American Sign Language (ASL) Hand Gesture Recognition System** built using **Python**, **OpenCV**, and **MediaPipe**. This project detects hand landmarks from webcam input and recognizes specific ASL gestures using hand landmark analysis.

---

## Project Overview

This project aims to recognize hand gestures in real time using computer vision and machine learning techniques. The system captures live video through a webcam, detects hand landmarks, analyzes finger positions, and identifies predefined ASL gestures.

The system currently recognizes the following gestures:

- ILY (I Love You)
- Yes (Fist)
- Thumbs Up
- Number 1

The recognized gesture is displayed directly on the video stream.

---

## Features

- Real-time webcam-based hand tracking
- Hand landmark detection using MediaPipe
- Gesture classification using custom logic
- Low latency recognition
- Visual landmark plotting
- Easy to extend with new gestures
- Lightweight and fast execution

---

## Tech Stack

### Python
Main programming language used for:
- Computer vision
- Logic implementation
- Gesture classification

### OpenCV
Used for:
- Webcam access
- Frame processing
- Image rendering
- Display output

### MediaPipe
Used for:
- Hand detection
- Hand landmark extraction
- Real-time tracking

---

## How It Works

The system works in the following steps:

### Step 1: Capture Video
The webcam captures live frames using OpenCV.

```python
import cv2
cap = cv2.VideoCapture(0)
```

---

### Step 2: Hand Detection
MediaPipe detects the hand and identifies 21 hand landmarks.

```python
import mediapipe as mp

mp_hands = mp.solutions.hands
hands = mp_hands.Hands()
```

Each landmark represents an important joint or fingertip of the hand.

Landmark examples:
- Thumb tip
- Index fingertip
- Wrist
- Finger joints

---

### Step 3: Landmark Extraction
Coordinates of each landmark are extracted.

Example:

```python
for id, lm in enumerate(hand_landmarks.landmark):
    h, w, c = frame.shape
    cx, cy = int(lm.x * w), int(lm.y * h)
```

These coordinates help determine finger positions.

---

### Step 4: Gesture Recognition
Gesture logic compares finger states:
- Open
- Closed
- Bent
- Extended

Example:

```python
if thumb_up:
    gesture = "Thumbs Up"
```

Custom rules determine which gesture is being shown.

---

## Recognized Gestures

---

### 1. ILY (I Love You)

Gesture Condition:
- Thumb open
- Index open
- Pinky open
- Middle closed
- Ring closed

Output:

```text
ASL: ILY (I Love You)
```

---

### 2. Yes (Fist)

Gesture Condition:
- All fingers folded

Output:

```text
ASL: Yes (Fist)
```

---

### 3. Thumbs Up

Gesture Condition:
- Thumb extended upward
- Other fingers closed

Output:

```text
ASL: Thumbs Up
```

---

### 4. Number 1

Gesture Condition:
- Index finger open
- All others closed

Output:

```text
ASL: Number 1
```

---

## Project Structure

```bash
ASL-Gesture-Recognition/
│
├── main.py
├── gesture_detector.py
├── requirements.txt
├── README.md
└── assets/
```

---

## Installation

Clone repository:

```bash
git clone https://github.com/your-username/asl-gesture-recognition.git
```

Move into folder:

```bash
cd asl-gesture-recognition
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Requirements

```txt
opencv-python
mediapipe
numpy
```

Install manually:

```bash
pip install opencv-python mediapipe numpy
```

---

## Running the Project

Run:

```bash
python main.py
```

The webcam will open and start detecting gestures.

Press:

```text
Q
```

to exit.

---

## Sample Output

### Hand Landmark Detection
- Green dots represent landmarks
- Numbers indicate landmark IDs

### Gesture Recognition Output
Examples:

```text
ASL: ILY (I Love You)
ASL: Yes (Fist)
ASL: Thumbs Up
ASL: Number 1
```

---

## Advantages

- Real-time detection
- High accuracy for supported gestures
- Easy to scale
- Beginner-friendly implementation
- Useful for sign language applications

---

## Limitations

- Limited gesture vocabulary
- Sensitive to poor lighting
- Recognition accuracy depends on hand angle
- Complex gestures may need ML model training

---

## Future Improvements

Future enhancements may include:

- Support for full ASL alphabet
- Deep learning gesture classifier
- Voice output
- Sentence formation
- Mobile app deployment
- Gesture dataset training

---

## Applications

This system can be used in:

- Sign language learning
- Human-computer interaction
- Accessibility systems
- Smart assistants
- Educational tools
- AI-based communication systems

---

## Conclusion

The ASL Hand Gesture Recognition System demonstrates how computer vision and machine learning can improve communication through sign language recognition. By combining OpenCV and MediaPipe, the system provides fast and accurate real-time gesture recognition with minimal hardware requirements.

This project serves as a strong foundation for building more advanced sign language recognition systems.
