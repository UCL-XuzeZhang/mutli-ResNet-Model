# mutli-ResNet-Model

## Project Introduction

### What is it?
A one-stop construction of multiple ResNet models (ResNet16, ResNet18, ResNet34, ResNet50, ResNet101, ResNet152) to predict gravitational waves.

###  Why do it?
The ResNet (Residual Network) model is widely used in the field of deep learning. It was proposed by Kaiming He and others in 2015. The primary innovation of ResNet lies in its residual connections (or skip connections), allowing the network to effectively train at deeper levels. Here are some key advantages of the ResNet model:

- Mitigating Gradient Vanishing: By introducing skip connections, ResNet alleviates the gradient vanishing problem common in deep networks. This allows the network to achieve deeper architectures without sacrificing training stability.

- Accelerated Training: Due to the existence of residual blocks, each layer can directly access features from previous layers. This aids in speeding up convergence.

- Ease of Optimization: Compared to traditional deep networks, deep residual networks with skip connections are simpler to optimize. In fact, as network depth increases, ResNet's training error remains constant or even decreases, whereas the training error for traditional networks increases.

- Deeper Models: With ResNet, researchers have been able to train neural networks with over 1000 layers, something previously thought to be unimaginable. Deeper networks can capture more complex features.

- Parameter Efficiency: While ResNet can be very deep, its parameter count doesn't always increase linearly with its depth. This means ResNet can achieve impressive performances while keeping the number of parameters relatively low.

- Broad Applicability: ResNet performs excellently not only in image classification tasks but also in many other computer vision tasks, such as object detection and semantic segmentation.

- Easy Integration: Due to its simple and modular structure, residual blocks can be easily integrated into other network architectures.

###  How to do it?
Building a ResNet model involves stacking residual blocks. The primary idea behind a residual block is to add a skip connection in each block. This connection allows the input to bypass intermediate layers and directly pass to the output, aiding optimization and mitigating the gradient vanishing issue. For specifics, please refer to the model construction section in the provided PDF and Jupyter notebook.


## Python packages

numpy: Stands for Numerical Python. It's the core library for numerical computing in Python. Provides a high-performance multidimensional array object and tools for working with these arrays.

tensorflow: An open-source machine learning library developed by Google. It's used for both research and production in companies/academies. tf.__version__ is used to check the version of TensorFlow being used.

keras: An open-source software library that provides a Python interface for artificial neural networks. Keras acts as an interface for the TensorFlow library.

layers, Sequential, optimizers: These are sub-modules of TensorFlow's Keras API. They provide building blocks for constructing neural networks (layers), a way to linearly stack layers (Sequential), and optimization algorithms (optimizers) to train these networks.

random: This module implements pseudo-random number generators for various distributions. It can be used for tasks like shuffling data.

pandas: An open-source data analysis and manipulation tool. It offers data structures and operations for manipulating numerical tables and time series.

matplotlib.pyplot: A module in the Matplotlib library for plotting a wide variety of static, animated, and interactive visualizations in Python.

math: This module provides access to the mathematical functions defined by the C standard. It includes functions like sqrt, sin, cos, etc.

collections: This module provides alternatives to built-in types that provide additional functionality. Examples include namedtuple, deque, Counter, etc.

os: This module provides a portable way of using operating system-dependent functionality like reading or writing to the file system.

logging: Used for logging messages in a flexible way. It can log to different outputs including the console, files, etc.

datetime: Provides classes for manipulating dates and times. It can be used to get the current date and time, perform arithmetic on dates, etc.

## Datasets

### [Dataset Source: G2Net Gravitational Wave Detection on Kaggle](https://www.kaggle.com/competitions/g2net-gravitational-wave-detection/data)

### Description:

The dataset provides time series data of simulated gravitational wave measurements from three interferometers: LIGO Hanford, LIGO Livingston, and Virgo.
Each time series includes either just detector noise or detector noise combined with a simulated gravitational wave signal. The objective is to determine when a signal (target=1) is in the data.
The exact waveform of a binary black hole is influenced by 15 parameters, such as masses, location, distance, and spins. These have been randomized based on astrophysically driven prior distributions for the simulated signals but aren't part of the competition data.
Every data sample (.npy file) comprises 3 time series (one for each detector). Each series lasts 2 seconds and is sampled at 2,048 Hz.
The integrated signal-to-noise ratio (SNR) is crucial for determining a signal's detectability. A signal is typically considered detectable when the integrated SNR is more than ~8. This isn't the same as instantaneous SNR. Unlike the GW150914 detection, these signals usually aren't discernible by just viewing the time series.

### Files:

train/: Training set with one .npy file per observation. Labels are in the files mentioned below.

test/: Test set. Predict the likelihood that the observation contains a gravitational wave.

training_labels.csv: Indicates if the corresponding signal has a gravitational wave.

sample_submission.csv: A template for submissions in the correct format.


## Training and Output

Due to the multiple models created having many parameters, even the smallest model requires over a day for training. By training multiple models, the best predictive data is generated, achieving an accuracy of 0.87. For detailed prediction results, please refer to the file "final prediction with accuracy of 0.87".





