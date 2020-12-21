# gans-on-image-classification
This is a machine learning in-class project that applies GANs on the task of image classification. GAN is originally used for generating real-like images through the competing training of generator and discriminator. At here, after it is trained over many epochs, we use transfer learning and fine-tuning to adapt it into 10-way classification on MNIST dataset. 

## files
- `cnn.ipynb` is the conventional convolutional neural network that uses tensorflow and keras to train and test on MNIST dataset
- `gan.ipynb` is the generative adversarial network adapted from the DCGAN on tensorflow website
- `report gan assignment.pdf` is the report file that describes the project details
- `trial_1.ipynb`, `trial_2.ipynb`, `trial_3.ipynb` are three different trials that use different transfer learning and fine-tuning techniques on the discriminator from the trained GANs; their descriptions are specified in the report
