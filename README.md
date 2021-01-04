# gans-on-image-classification
This is a machine learning/deep learning project that applies GANs on the task of image classification. GAN is originally used for generating real-like images through the competing training of generator and discriminator. At here, after it is trained over many epochs, we use transfer learning and fine-tuning to adapt it into 10-way classification on MNIST dataset. 

## Files
- `cnn.ipynb` is the conventional convolutional neural network that uses tensorflow and keras to train and test on MNIST dataset
- `gan.ipynb` is the generative adversarial network adapted from the DCGAN on tensorflow website
- `report gan assignment.pdf` is the report file that describes the project details
- `trial_1.ipynb`, `trial_2.ipynb`, `trial_3.ipynb` are three different trials that use different transfer learning and fine-tuning techniques on the discriminator from the trained GANs; their descriptions are specified in the report

## Comparison
### Between transfered GAN and conventional CNN
With 10000 training size and 10000 testing size, the transfered and fine-tuned GAN discriminator can reach 94% training and validation accuracy. The conventional CNN, with the last two layers kept as the same structure as the transfered discriminator, reaches 96% training and validation accuracy with the same training and testing sets. This means that the two approaches achieve very similar performance. The transfered discriminator has slightly lower accuracy, but it allows for more versatality as the trained GANS can also be used for generating new real-like digits. And, with more training epochs of GAN, our accuracy might continue increasing and reach the same value as CNN.

### Between transfered GAN and conventional PCA & KNN algorithm
This comparison is more interesting than the one above. One reason for that is the two methods can hardly be compared with each other. Transferred GAN is deep learning technique, while PCA & KNN are conventional machine learning algorithm (the implementation can be found in [another repository](https://github.com/ck44liu/eigenvalue-for-mnist-classification)). When both training size and testing size are 1000, PCA & KNN actually performs better (its validation accuracy reaches 90%, while the transfered discriminator is 87% and conventional CNN is 80%). However, PCA & KNN approach suffers from computational cost as data size increases. Even a training size of 2000 won't finish running for a long time. Deep neural network runs significantly faster than conventional machine learning approach when data size gets large. This also confirms the advantage of deep learning, namely that it starts to shine when dealing with large datasets.

## Update
Added `trained_weights` into Releases. It contains the trained weights (checkpoints) of generator and discriminator over 50 epochs on 10000 MNIST digits. Though it is a relatively small model, it already achieves decent performance on digits classification as described above. It would be interesting to see how the discriminator, or the generator, can be transfered and applied to other kinds of tasks.
