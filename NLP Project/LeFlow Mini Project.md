#a7-50t #project 

## Synopsis

Using LeFlow to create a RTL implementation for a simple number classification model

## Functionality Report

- RTL implementation will be generated from a Tensorflow project using LeFlow.
- Model will take an image of a hand drawn number and output (in binary) the guess for that number, using the leds on board the A7-50T
## Components Needed

- LeFlow
- TensorFlow
- A7-50T

## Process

- Need to research [[Creating a Model with Tensorflow]]
- Develop a classification model for determining numbers in handwritten images
	- Will need to encode image into binary data, for testing with hardware
- Test model (Python)
- Generate RTL using LeFlow
- Test RTL model using set images (images will be encoded into binary?)

## Resources
- [Keras MNIST](https://keras.io/examples/vision/mnist_convnet/) 
- [Geek Keras](https://www.geeksforgeeks.org/mnist-dataset/)
- [[Python Version and Environment Control]]
- [Tensorflow Tut](https://youtu.be/5Ym-dOS9ssA?si=VY0pJZxWDpK6kn1R)
- [Layers Explained](https://www.geeksforgeeks.org/keras-layers-api/)
- [[Loss Function]]
- [[Optimizers]]
## Notes 

- Francois Chollet
- Use Claude for creating tutorial (jupyter notebooks, visualization)
- Implement `tensorflow-metal` python plugin for acceleration on mac