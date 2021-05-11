# Deep-Learning
This repo is divided into three parts; they are:

1. Visualizing Convolutional Network Filters
2. Visualizing heatmaps of class activation
3. Visualizing intermediate activations


# Visualizing convnet filters
Easy thing to do, to inspect the filters learned by convnets is to display the visual pattern that each filter is meant to respond to. This can be done with gradient ascent in input space: applying gradient descent to the value of the input image of a convnet so as to maximize the response of a specific filter, starting from a blank input image. The resulting input image would be one that the chosen filter is maximally responsive to.

![visualization 1](https://user-images.githubusercontent.com/38569017/117828093-d20c4480-b271-11eb-9402-b4f61630e94d.png)


# Visualizing heatmaps of class activation
I will introduce one more visualization technique, one that is useful for understanding which parts of a given image led a convnet to its final classification decision. This is helpful for "debugging" the decision process of a convnet, in particular in case of a classification mistake. It also allows you to locate specific objects in an image.

This general category of techniques is called "Class Activation Map" (CAM) visualization, and consists in producing heatmaps of "class activation" over input images. A "class activation" heatmap is a 2D grid of scores associated with an specific output class, computed for every location in any input image, indicating how important each location is with respect to the class considered. For instance, given a image fed into one of our "cat vs. dog" convnet, Class Activation Map visualization allows us to generate a heatmap for the class "cat", indicating how cat-like different parts of the image are, and likewise for the class "dog", indicating how dog-like differents parts of the image are.

![heat maps](https://user-images.githubusercontent.com/38569017/117828504-27e0ec80-b272-11eb-9e02-7c5987702575.png)

# Visualizing intermediate activations
Visualizing intermediate activations consists in displaying the feature maps that are output by various convolution and pooling layers in a network, given a certain input (the output of a layer is often called its "activation", the output of the activation function). This gives a view into how an input is decomposed unto the different filters learned by the network. These feature maps we want to visualize have 3 dimensions: width, height, and depth (channels). Each channel encodes relatively independent features, so the proper way to visualize these feature maps is by independently plotting the contents of every channel, as a 2D image.

![intermediate](https://user-images.githubusercontent.com/38569017/117828888-8ad28380-b272-11eb-872f-ad10cd4a0a35.png)

