# Image-Recognition-System

## This documentation outlines the Image Recognition System that enables users to add images for the system to train on, extract facial details, recognize individuals in new images the system has not previously encountered, and finally, compile a dataset detailing all the users the system has been trained on.

## Features

- **Face Detection**: Detect faces in a given image or a folder containing multiple images. This function is optional and can be used as a preliminary step for face recognition.
  > The system initially detects faces within images. This step employs a Histogram of Oriented Gradients (HOG) algorithm combined with a linear classifier, an image pyramid, and a sliding window detection scheme. The HOG feature descriptor is used for object detection due to its effectiveness in capturing edge or gradient structure that is characteristic of local shape.

- **Person Addition**: Add new persons to the dataset for future recognition.
- **Person Recognition**: Recognize persons already added to the dataset in new, unseen images.
- **Dataset Overview**: Generate a comprehensive dataframe that includes the number of images, IDs, and names for each person in the dataset.

## Getting Started

To use the Image Recognition System, follow the steps outlined below:

### Prerequisites

Ensure you have the necessary libraries installed, including `face_recognition`, `cv2` (OpenCV), `numpy`, and `pandas`.

```bash
pip install face_recognition opencv-python numpy pandas
```

## Example Usage

### Example usage of detect_faces
```detect_faces('/path/to/image_or_folder')```

### Example usage of add_person
```add_person('/path/to/person_folder')```

### Example usage of recognize_person
```recognize_person('/path/to/new/image.jpg')```

### Example usage of create_dataset_dataframe
```create_dataset_dataframe()```


Face Detection

Face Encoding
After detecting a face in an image, the system needs to understand it in a way that it can be compared to other faces. This involves creating a face encoding, which is essentially a way to represent the face as a vector of numbers. A popular method for face encoding is through the use of Deep Convolutional Neural Networks (CNN). The dlib library's face recognition model, which is based on a ResNet-34 network architecture, is an example that transforms faces into 128 unique numbers (or embeddings). Each number in this vector aims to capture some variance of the faces seen during the training phase, enabling the system to distinguish between different faces effectively.

Face Recognition
For the recognition part, the system compares the face encoding of the new image with encodings from known faces in the dataset. This comparison relies on distance metrics, Euclidean distance, to find the closest match. If the distance between the new face encoding and any encoding from the dataset is below a certain threshold, the faces are considered to be of the same person. This mechanism enables the system to recognize individuals in new images.

Dataset Management and Learning
The system manages a dataset of known faces by storing their encodings and corresponding identities. Adding a new person to the dataset involves processing their images to generate face encodings and updating the dataset with these new encodings. This process allows for incremental learning, where the system can improve and expand its recognition capabilities as more faces are added.
