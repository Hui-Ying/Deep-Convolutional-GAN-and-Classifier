# Deep-Convolutional-GAN-and-Classifier
## Description:
This project was originally a class project from EEC206 in 2020 spring quarter at UC Davis.  
In order to further improving the results(and for fun), I decided to continue working on this project.

Project goal: Implementation of a specific type of GAN designed to process images, called a Deep Convolutional GAN (DCGAN). The DCGAN was trained to generate natural images from CIFAR10. 



## Contents: 
- Implementation of DCGAN
- Discriminator 
- Generator 
- Combination of Discriminator and Generator

- Classifier architecture c

- Train the DCGAN to generate natural images from CIFAR10.


- Use the dataset generated from the generator to train the classifier c’


- Color map implementation


## Brief introduction of GAN:

- Generator is an upsampling neural network, with an input of a 1D tensor, after the neural network, the output will be a higher dimensional tensor. The generator will produce fake images, and keep improving the result based on the judge of the discriminator. The fake image produced by the generator aims to obtain a higher score from the discriminator. 


- Discriminator is a regressor, giving a continuous number(or 0/1) as an output with the input from the generator. For example, if the discriminator detects that the input is a real image, then it will give a 1 at the output, on the other hand, if it’s detected as a fake image, then it will give a 0 to the output. If the discriminator converges to 0.5, meaning that the discriminator fails to distinguish between the fake and real image. In general, we want the loss for the discriminator to be as high as possible because it indicates how well the generator is capable of producing real-alike images.

- The main training process of GAN: 
The discriminator is trained with real images.
An input of 1D noise vector as input to the generator, and the generator produces fake images at the output.
The fake images aan real images are fed into the discriminator and the discriminator starts the process of recognizing real and fake images, and gives a score at the output to indicate how well the generator can produce a real-alike image. 
The score indicates a feedback to the generator, with this feedback, the generator starts changing its weights and learning how to generate real-alike images.
The whole process can be found in the figure below[[2]](https://pathmind.com/wiki/generative-adversarial-network-gan).   

![](/images/GAN.png)



- Generator structure:
3 convolutional layers

- Discriminator structure: 
4 convolutional layers and 1 FC layer 

## Classifier CNN architecture:

Here we compare two classifiers c and c’. 

- Classifier c: The dataset used to train the classifier c is from cifar10.
The architecture contains 4 convolutional layers and with kernel size 3x3.
2x2 pooling layer is added after every two convolutional layers(con-con-pool scheme)
LeakyRelu activation is added after all the convolutional and dense layers


- Classifier c’: The dataset used to train the classifier c’ is from the DCGAN. 
Architecture is the same as the classifier c. 


## Some helpful information about GAN:
[1][A Brief Introduction To GANs](https://medium.com/sigmoid/a-brief-introduction-to-gans-and-how-to-code-them-2620ee465c30)  
[2][A Beginner's Guide to Generative Adversarial Networks (GANs)](https://pathmind.com/wiki/generative-adversarial-network-gan)

