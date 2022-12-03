TinyML can be defined as a subfield of ML which pursues enabling ML applications on devices that are cheap, as well as resource- and power-constrained.

The objective of TinyML is to bring machine learning to the edge in an extreme way, where battery-powered, microcontroller-based embedded devices can perform ML tasks with real-time responsivity. This effort is extraordinarily multidisciplinary, requiring optimization and maximization from fields including hardware, software, data science, and machine learning.

An example of a TinyML application in daily life is the audio wake-word detection model used inside of Google and Android devices. In order to “turn on” when they hear the words “OK Google,” Android devices use a 14 kB speech detection ML model that runs on a DSP. The same can be said for many other virtual assistants.

Pete Warden, widely considered the father of TinyML, states that TinyML should aim to operate at a power consumption below 1 mW. The reason for this seemingly arbitrary number is that 1 mW consumption makes a device capable of running on a standard coin battery with a reasonable lifetime of months to a year.

# Tensorflow

TensorFlow is a free and open-source software library for machine learning and artificial intelligence. It can be used across a range of tasks but has a particular focus on training and inference of deep neural networks.

# Tensorflow Lite

TensorFlow Lite has APIs for mobile apps or embedded devices to generate and deploy TensorFlow models. These models are compressed and optimized in order to be more efficient and have a higher performance on smaller capacity devices.

Generally speaking, the most popular and built-out ecosystem for TinyML development is TensorFlow Lite for Microcontrollers (TF Lite Micro).

> TensorFlow Lite for Microcontrollers is designed to run machine learning models on microcontrollers and other devices with only a few kilobytes of memory. The core runtime just fits in 16 KB on an Arm Cortex M3 and can run many basic models. It doesn't require operating system support, any standard C or C++ libraries, or dynamic memory allocation.

The following steps are required to deploy and run a TensorFlow model on a microcontroller:

1.  Train a model:
    -   Generate a small TensorFlow model that can fit your target device and contains supported operations.
    -   Convert to a TensorFlow Lite model using the TensorFlow Lite converter.
    -   Convert to a C byte array using standard tools to store it in a read-only program memory on device.
3.  Run inference on device using the C++ library and process the results.

![https://www.makeuseof.com/what-is-tensorflow-lite-and-how-is-it-a-deep-learning-framework/](https://static1.makeuseofimages.com/wordpress/wp-content/uploads/2021/05/General-Work-Flow-for-TensorFlow-Lite-Micro.jpg?q=50&fit=crop&w=943&dpr=1.5)

The training process of the neural network requires high computational hardware. Thus, it is trained on the general TensorFlow model. However, training is only required if a custom dataset fits a deep learning model, whereas pre-trained models on the framework can also be used for the applications.

The process is followed by converting the TensorFlow model to hardware compatible TensorFlow Lite model in the .tflite format. Most of the microcontroller's firmware do not support the native filesystem for directly embedding the flat buffer format of the TensorFlow Lite model. Hence, the conversion of the .tflite file is necessary to an array structure format, which is compatible with the microcontrollers.

![](https://static1.makeuseofimages.com/wordpress/wp-content/uploads/2021/05/Development-Boards-Supporting-TensorFlow-Lite-Micro.png?q=50&fit=crop&w=943&dpr=1.5)