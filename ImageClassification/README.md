# Image Classification with TensorFlow

A simple image classification project built with TensorFlow and Keras.

This project was completed as a hands-on learning exercise to understand the complete deep learning workflow, including:

* Data collection and preprocessing
* Building a Convolutional Neural Network (CNN)
* Training and validation
* TensorBoard monitoring
* Model saving and loading
* Image inference

## Learning Resource

This project was implemented by following the tutorial series created by Nick Nochnack:

GitHub Repository:
https://github.com/nicknochnack/ImageClassification

The tutorial provided an excellent introduction to practical image classification using TensorFlow.

## Environment

The original tutorial was created in 2022.

To reproduce the project in 2026, several compatibility fixes were required due to changes in Python, TensorFlow, and Keras.

Main environment:

* Python 3.11
* TensorFlow 2.21
* Keras 3.14
* OpenCV
* Matplotlib

A detailed description of all compatibility fixes is provided below.

## Training Hardware

The project was trained and tested entirely on CPU.

Although the system contains an NVIDIA RTX 3060 Laptop GPU, TensorFlow versions newer than 2.10 no longer support native GPU acceleration on Windows.

Since this was a relatively small project and training time was acceptable, CPU execution was used instead of creating a dedicated TensorFlow 2.10 GPU environment.

## Project Structure

```text
ImageClassification/
│
├── data/
│   ├── happy/
│   └── sad/
│
├── models/
│
├── ImageClassification.ipynb
│
└── README.md
```

## Compatibility Fixes for Running the Project in 2026

### Python Version Compatibility

The original environment was not compatible with Python 3.13.

A dedicated virtual environment was created using Python 3.11:

```bash
py -3.11 -m venv imageclassification311
```

### Jupyter Kernel Reconfiguration

The Jupyter kernel initially pointed to the Anaconda Python installation instead of the project's virtual environment.

The kernel was recreated and linked to the correct interpreter.

### TensorFlow Installation Update

The original installation instructions referenced the legacy package:

```bash
pip install tensorflow-gpu
```

This package is no longer maintained.

The updated installation command is:

```bash
pip install tensorflow opencv-python matplotlib
```

### TensorBoard Dependency

TensorBoard was not automatically available in the environment and had to be installed manually:

```bash
pip install tensorboard
```

### Python Standard Library Deprecations

The project uses:

```python
import imghdr
```

which is deprecated and scheduled for removal in future Python versions.

### Keras Model Serialization

The tutorial saves models using:

```python
model.save("imageclassifier.h5")
```

Modern Keras versions recommend:

```python
model.save("imageclassifier.keras")
```

although the legacy HDF5 format still works.

## Results

The model was successfully trained and evaluated on the provided Happy vs Sad dataset.

## Acknowledgements

Special thanks to Nick Nochnack for creating the original tutorial and educational content that inspired this implementation.

