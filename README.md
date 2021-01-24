# GAN---Generate-Faces

In this project, you'll use generative adversarial networks to generate new images of faces.

Also, keep studying about the topic as this is just the beginning. I have also given some more tips to further improve your project.

Moreover, here're a few resources to help you continue this wonderful journey:

Wasserstein GAN as it's GAN with an objective and thus has a convergence criterion.
Generative Models in general
DiscoGAN, Discover Cross-Domain Relations with Generative Adversarial Networks
GAN stability
MNIST GAN with Keras which shows that how much concise can one be when modelling neural networks.
How to Train a GAN: https://github.com/soumith/ganhacks
Making pixel art with GANs.
Also go through current standard technique for making high resolution images: Progressive Growing of GANs for Improved Quality, Stability, and Variation

BigGANs: Large-Scale GAN Training is one of very influential papers of last year in generative modelling. TLDR: Twitter thread by the author.

Another interesting read is the Style-Based GAN. You can also see its results on the website thispersondoesnotexist.com.

A blog going through variety of GANs and comparing them

The function get_dataloader should transform image data into resized, Tensor image types and return a DataLoader that batches all the training data into an appropriate size.

Pre-process the images by creating a scale function that scales images into a given pixel range. This function should be used later, in the training loop.

The Discriminator class is implemented correctly; it outputs one value that will determine whether an image is real or fake.

implemented discriminator using conv2d + strides to avoid making sparse gradients instead of max-pooling layers.

used leaky_relu instead of ReLU for the same reason of avoiding sparse gradients as leaky_relu allows gradients to flow backwards unimpeded.

used sigmoid as output layer

implemented BatchNorm to avoid "internal covariate shift".

Implement dropouts with low drop_prob in discriminator as mentioned

The Generator class is implemented correctly; it outputs an image of the same shape as the processed training data.

This function should initialize the weights of any convolutional or linear layer with weights taken from a normal distribution with a mean = 0 and standard deviation = 0.02.

The loss functions take in the outputs from a discriminator and return the real or fake loss.

There are optimizers for updating the weights of the discriminator and generator. These optimizers should have appropriate hyperparameters.

The beta1 is a bit too high. Values like 0.1 to 0.3 have shown to get best results.

The current learning rate is okay but can be a bit high. The DCGAN with this architectural structure remains stable with lr between 0.0002 and 0.001.

Real training images should be scaled appropriately. The training loop should alternate between training the discriminator and generator networks.

The project generates realistic faces. 

