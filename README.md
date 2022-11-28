# Image-reconstruction-and-Anomaly-detection

CNN autoencoder is trained on the MNIST numbers dataset for image reconstruction. Anomaly detection is carried out by calculating the Z-score. The Machine Learning framework used is Keras.

# Autoencoders

An autoencoder is a special type of neural network that is trained to copy its input to its output. An
autoencoder first encodes the image into a lower
dimensional latent representation, then decodes the
latent representation back to an image. An
autoencoder learns to compress the data while
minimizing the reconstruction error.


![The-structure-of-proposed-Convolutional-AutoEncoders-CAE-for-MNIST-In-the-middle-there](https://user-images.githubusercontent.com/117833435/204174827-0900d4d6-8bfa-4dda-895c-db577c0c5166.png)


# Dataset

The data set used for this project is the MNIST data
set. The MNIST database (Modified National Institute
of Standards and Technology database) is a large
database of handwritten digits and fashion images.

# Autoencoder Model

The model architecture used for image reconstruction is the Convolution Neural network Autoencoder.
There are two key components in an autoencoder:
-Encoder: Learns how to compress the original input into a small encoding
-Decoder: Learns how to restore the original data from that encoding generated by the Encoder

The encoder model consists of two convolution layers followed by a max-pooling subsampling. The 3 x 3 kernels
and ReLU activations are also used.
The decoder takes the tensor having the sizes of (None, 4, 4, 8) from the encoder and passes it through
convolutional layers followed by up-sampling. The reconstructed tensor has the same size as that of the input
image.

CNN autoencoder is trained on the MNIST data set . Model is compiled and trained with Adam optimizer, binary
cross-entropy error loss, and a batch size of 60 for 50 epochs.


# Anomaly detection

As mentioned above that the MNIST handwritten digits data set has been used to carry out image reconstruction, the fashion MNIST data set has been used as an anomaly in order to perform anomaly detection and calculate the accuracy of our algorithm.

The process of anomaly detection was carried out through the calculation of Z-score. Based on the reconstruction error for each image, the Z-score is calculated using the following calculations.

mean = summation of all the reconstruction errors/ number of input image samples  
standard deviation = sqrt[( reconstruction error - mean) * ( reconstruction error - mean)]  
Threshold (upper limit) = mean + (3 * standard deviation)  
Threshold (lower limit) = mean - (3 * standard deviation)  
reconstruction error = binary cross-entropy loss between the original image and reconstructed image.  
If reconstruction error < Threshold (lower limit) OR reconstruction error > Threshold (upper limit) the anomaly is
detected.
