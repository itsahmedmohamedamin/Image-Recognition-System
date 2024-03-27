# Image-Recognition-System

## This documentation outlines the Image Recognition System that enables users to add images for the system to train on, extract facial details, recognize individuals in new images the system has not previously encountered, and finally, compile a dataset detailing all the users the system has been trained on.

## Features

- **Face Detection**: Detect faces in a given image or a folder containing multiple images. This function is optional and can be used as a preliminary step for face recognition.
- **Person Addition**: Add new persons to the dataset for future recognition.
- **Person Recognition**: Recognize persons already added to the dataset in new, unseen images.
- **Dataset Overview**: Generate a comprehensive dataframe that includes the number of images, IDs, and names for each person in the dataset.

## Getting Started

To use the Image Recognition System, follow the steps outlined below:

### Prerequisites

Ensure you have the necessary libraries installed, including `face_recognition`, `cv2` (OpenCV), `numpy`, and `pandas`.

```bash
pip install face_recognition opencv-python numpy pandas
