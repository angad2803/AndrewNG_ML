# Convolutional Neural Networks

Problem: So far our classifiers don’t respect the spatial structure of images!

Solution: Define new computational nodes that operate on images!

![alt text](image-34.png)

A fully connected layer looks at the entire image as one long list of numbers and learns weighted combinations of all pixels to decide between classes

![alt text](image-35.png)

The filter slides over the image, left-to-right and top-to-bottom.

At each location:

It computes a dot product between the filter weights and the overlapping patch of the image (size 3×5×5 = 75 numbers).

Produces 1 number (activation).

Repeat this sliding for all possible positions → builds the activation map.

![alt text](image-37.png)

Each conv layer adds depth (more filters → more feature maps).

But each layer shrinks spatial size (because no padding is used).

The filter shape always matches the depth of the input, but spatial size (3×3, 5×5, etc.) is chosen by us.

👉 It’s like each layer looks for increasingly abstract features:

First: edges, colors (6 filters).

Second: corners, textures (10 filters).

Third: object parts (12 filters).

What do convolutional filters learn?

![alt text](image-38.png)

For convolution with kernel size K, each element in the output depends on a K x K receptive field in the input

![alt text](image-39.png)

![alt text](image-41.png)

![alt text](image-40.png)

## Pooling layers

Another way to downsample

![alt text](image-42.png)

## Batch Normalization

Idea: “Normalize” the outputs of a layer so they have zero mean and unit variance

![alt text](image-43.png)

This is a differentiable function, so we can use it as an operator in our networks and backprop through it

Problem: What if zero-mean, unit variance is too hard of a constraint?

![alt text](image-44.png)

Problem: Estimates depend on minibatch; can’t do this at test-time!

![alt text](image-45.png)

Training → BN relies on minibatch stats to stabilize optimization.

Testing → BN relies on the population statistics (approximated by running averages collected during training)

![alt text](image-46.png)

![alt text](image-47.png)
