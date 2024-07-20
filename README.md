<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER/README_INSTRUCTIONS">
    <img src="https://srmsigkddtesting.vercel.app/static/media/srmsigkdd.23f2521d9133f1a1056f.png" alt="Logo" width="150" height="150">
  </a>

  <p align="center">
    Title of the project
    <br />
    <a href="https://github.com/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER/README_INSTRUCTIONS"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="Usage-Problem-Statement-and-Your-solution">View Demo</a>
    ·
    <a href="https://github.com/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER/README_INSTRUCTIONS/issues">Report Bug</a>
    ·
    <a href="https://github.com/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER/README_INSTRUCTIONS/issues">Request Feature</a>
  </p>
</p>

![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat) 
![contributions welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat) 
![Forks](https://img.shields.io/github/forks/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER/README_INSTRUCTIONS.svg)
![Issues](https://img.shields.io/github/issues/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER/README_INSTRUCTIONS.svg)
![PR](https://img.shields.io/github/issues-pr/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER/README_INSTRUCTIONS.svg)
![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)
![Views](https://views.whatilearened.today/views/github/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER/README_INSTRUCTIONS.svg)
![GitHub repo size](https://img.shields.io/github/repo-size/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER/README_INSTRUCTIONS)

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
      <ul>
        <li><a href="#dependencies">Dependencies</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#authors">Authors</a></li>
    <li><a href="#acknowledgements">Acknowledgements</a></li>
  </ol>
</details>



<!-- ABOUT THE PROJECT -->
## About The Project
In Generative Adversarial Networks, two networks train against each other. The generator misleads the discriminator by creating compelling fake inputs. The discriminator tells if an input is real or artificial.
### There are 3 major steps in the training:

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

# Built With
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-%23D00000.svg?style=for-the-badge&logo=Keras&logoColor=white)


### Dependencies

Here, list all libraries, packages and other dependencies that need to be installed to run your project. Include library versions and how they should be installed if a special requirement is needed.

> Make sure you make requirements.txt having all the dependencies required to run the code

For example, this is how you would list them:
* Installing all dependencies
  ```sh
  pip install -r requirements.txt
  ```
* Example of requirements.txt
  ```sh
  tensorflow
  opencv-python
  keras
  numpy
  ```

<!-- USAGE EXAMPLES -->
## Usage - Problem Statement and Your solution

Use this space to show useful examples of how a project can be used. For course projects, include which file to execute and the format of any input variables.

Additional screenshots, code examples and demos work well in this space. You may also link to more resources.

_For more examples, please refer to the [Documentation](https://example.com)_

<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.


<!-- Authors -->
## Authors

Your Name - [@your_twitter](https://twitter.com/your_username) - email@example.com

Project Link: [https://github.com/your_username/repo_name](https://github.com/your_username/repo_name)


<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements

You can acknowledge any individual, group, institution or service.
* [SRM KTR SIGKDD Student Chapter](https://github.com/ACM-SIGKDD-SRM-KTR-STUDENT-CHAPTER)
* [Theodo DATA and AI](https://data-ai.theodo.com/)

