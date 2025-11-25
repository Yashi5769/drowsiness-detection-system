# Drowsiness Detection System

A computer vision project implemented in Python that detects driver drowsiness and yawning in real-time. This system monitors the user's eyes and mouth using facial landmarks to alert them if they appear drowsy or are yawning.

## Features

* **Eye Aspect Ratio (EAR):** Detects if eyes are closed for a prolonged period (drowsiness).
* **Mouth Aspect Ratio (MAR):** Detects yawning.
* **Real-time alerting:** Uses computer vision to monitor the face via webcam.

## Files Description

* `drowsiness_yawn.py`: The main Python script containing the logic for detection and alerting.
* `shape_predictor_68_face_landmarks.dat`: Pre-trained model by Dlib to detect 68 facial landmarks.
* `haarcascade_frontalface_default.xml`: OpenCV Haar Cascade classifier for face detection.

## Prerequisites

Ensure you have Python installed. You will need the following libraries:

* Python 3.x
* OpenCV (`cv2`)
* Dlib
* Imutils
* Scipy
* Numpy

You can install the dependencies using pip:

```bash
pip install opencv-python dlib imutils scipy numpy
```

> **Note:** Installing `dlib` might require CMake to be installed on your system.

## Usage

1.  **Clone the repository**
    ```bash
    git clone [https://github.com/Yashi5769/drowsiness-detection-system.git](https://github.com/Yashi5769/drowsiness-detection-system.git)
    cd drowsiness-detection-system
    ```

2.  **Download the Dlib Predictor**
    Ensure `shape_predictor_68_face_landmarks.dat` is present in the project directory. If it is not included or needs to be re-downloaded, you can get it from [dlib.net](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2) (extract it after downloading).

3.  **Run the System**
    Execute the main script to start the webcam feed and detection:
    ```bash
    python drowsiness_yawn.py
    ```

4.  **Controls**
    * Press `q` to quit the application.

## How it Works

* **Face Detection:** The system uses `haarcascade_frontalface_default.xml` (or Dlib's detector) to locate the face.
* **Landmark Detection:** Dlib's `shape_predictor_68_face_landmarks.dat` maps 68 points on the face.
    
* **Metric Calculation:**
    * **EAR (Eye Aspect Ratio)** is calculated to check if eyes are closed.
    * **MAR (Mouth Aspect Ratio)** is calculated to check if the mouth is open (yawning).
* **Alert:** If the calculated ratios cross a predefined threshold for a specific number of frames, an alert (text or sound) is triggered.
