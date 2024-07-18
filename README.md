#Image Deblurring Using GAN
##ABOUT THE PROJECT
In Generative Adversarial Networks, two networks train against each other. The generator misleads the discriminator by creating compelling fake inputs. The discriminator tells if an input is real or artificial.
###There are 3 major steps in the training:
use the generator to create fake inputs based on noise
train the discriminator with both real and fake inputs
train the whole model: the model is built with the discriminator chained to the generator.

The reason for chaining both networks is that there is no possible feedback on the generator’s outputs. Our only measure is whether the discriminator accepted the generated samples
The generator aims at reproducing sharp images. The network is based on ResNet blocks. It keeps track of the evolutions applied to the original blurred image. 
The objective is to determine if an input image is artificially created. Therefore, the discriminator’s architecture is convolutional and outputs a single value.
The last step is to build the full model. A particularity of this GAN is that inputs are real images and not noise. Therefore, we have a direct feedback on the generator’s outputs.

We extract losses at two levels, at the end of the generator and at the end of the full model.
The first one is a perceptual loss computed directly on the generator’s outputs. This first loss ensures the GAN model is oriented towards a deblurring task. It compares the outputs of the first convolutions of VGG
The second loss is the Wasserstein loss performed on the outputs of the whole model. It takes the mean of the differences between two images. It is known to improve convergence of generative adversarial networks.
Finally, we successively train the discriminator and the generator, based on both losses. We generate fake inputs with the generator. We train the discriminator to distinguish fake from real inputs, and we train the whole model.
##DEPENDENCIES
Keras
