# Driver Drowsiness Detection System

This project is a real-time system for detecting driver drowsiness using computer vision. It monitors the driver's eyes through a webcam and sounds an alarm if signs of fatigue are detected, helping to prevent accidents.

![Demo Screenshot of the Drowsiness Detection System in action](https://github.com/anij715/Driver-Drowsiness-Detection-System/blob/main/ddd.png)

## About The Project

This system was developed to address the significant safety problem of driver fatigue, which is a major cause of traffic accidents worldwide. Unlike alcohol or drugs, fatigue is difficult to measure, making technological solutions like this one crucial for improving road safety.

The core of this project is the calculation of the **Eye Aspect Ratio (EAR)**, a metric that can determine if a person's eyes are closed. If the EAR drops below a certain threshold for a sustained period, the system triggers an alert.

### Built With

* [Python](https://www.python.org/)
* [OpenCV](https://opencv.org/)
* [Dlib](http://dlib.net/)
* [Scipy](https://scipy.org/)
* [imutils](https://github.com/imutils/imutils)
* [playsound](https://github.com/TaylorSMarks/playsound)

## How It Works

1.  **Video Stream**: The system captures video from a webcam.
2.  **Face & Landmark Detection**: It uses dlib's pre-trained facial landmark detector to locate 68 key points on the driver's face.
3.  **Eye Extraction**: The coordinates of the left and right eyes are extracted from the facial landmarks.
4.  **EAR Calculation**: The Eye Aspect Ratio (EAR) is computed for both eyes. This ratio is the relationship between the height and width of the eyes.
5.  **Drowsiness Check**: If the EAR falls below a predefined threshold for a set number of consecutive frames, the system determines that the driver is drowsy.
6.  **Alarm**: An alarm sound is played to alert the driver.

$$\text{EAR} = \frac{\|\mathbf{p}_2 - \mathbf{p}_6\| + \|\mathbf{p}_3 - \mathbf{p}_5\|}{2\|\mathbf{p}_1 - \mathbf{p}_4\|}$$

## Getting Started

To get a local copy up and running, follow these simple steps.

### Prerequisites

You will need Python 3 installed on your system. You can install the required libraries using pip.

```sh
pip install numpy
pip install scipy
pip install opencv-python
pip install dlib
pip install imutils
pip install playsound
```

You will also need to download the pre-trained facial landmark predictor file:
* [**shape_predictor_68_face_landmarks.dat**](http://dlib.net/files/shape_predictor_68_face_landmarks.dat.bz2)

Unzip the file and place it in the project directory.

### Installation

1.  Clone the repo:
    ```sh
    git clone https://github.com/anij715/Driver-Drowsiness-Detection-System.git
    ```
2.  Navigate to the project directory:
    ```sh
    cd Driver-Drowsiness-Detection-System
    ```

## Usage

Run the `d3.py` script from your terminal. You must provide the path to the shape predictor file.

```sh
python d3.py --shape-predictor shape_predictor_68_face_landmarks.dat
```

To use a custom alarm sound, provide the path to the `.wav` file.

```sh
python d3.py --shape-predictor shape_predictor_68_face_landmarks.dat --alarm alarm.wav
```

Press the 'q' key to exit the program.

## Developers

* [Pratyush Agarwal](https://github.com/kyloprat)
* [Rizul Sharma](https://github.com/anij715)

This project was:
- Published as a review paper at EasyChair [(archived here)](https://easychair.org/publications/preprint/VST8), and
- Submitted in partial fulfillment of the requirements for the Bachelor's Degree in Computer Science & Engineering at KIIT University [(full report here)](https://www.researchgate.net/publication/336878674_DRIVER_DROWSINESS_DETECTION_SYSTEM).

## Citation
If you use this project in your research or work, please cite this github repo along with the original paper:

```latex
@booklet{EasyChair:2213,
  author    = {Pratyush Agarwal and Rizul Sharma},
  title     = {Driver Drowsiness Detection Techniques: Review},
  howpublished = {EasyChair Preprint 2213},
  year      = {EasyChair, 2019}}
```
