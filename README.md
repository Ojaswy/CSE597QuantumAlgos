# Project: Generative Adversarial Network (GAN) for Lattice-based Cryptography

Python version: 3.10.9

## Implementation
1. `pip install -r requirements.txt`
2. Run lwe_gan_main.ipynb via Jupyter (Command `<run in the same directory as the ipynb file>`: `jupyter notebook`)

## Objective
The goal of this project was to implement a Generative Adversarial Network (GAN) capable of generating samples representative of the Learning With Errors (LWE) distribution, a critical component in lattice-based cryptography.

## Background
Lattice-based cryptography relies on the hardness of certain problems associated with lattice structures for security. The Learning With Errors (LWE) problem is a cornerstone in this domain, involving the challenge of distinguishing between true LWE samples and random noise.

## Implementation Overview

### LWE Data Generation
- A function `generate_lwe_data_batch` was created to generate batches of LWE samples. It produces random binary secrets (`s`), random integer matrices (`a`), and computes the corresponding values (`b`) using modular arithmetic.
- A prime number `q` within the range of 2^15 and 2^30 is chosen for cryptographic robustness using the sympy library.

### GAN Architecture
- A GAN architecture was developed using TensorFlow and Keras. The generator network takes random noise as input and attempts to generate samples resembling LWE distributions.
- The discriminator network is designed to distinguish between real LWE samples and those generated by the generator.

### Training the GAN
- The GAN is trained by alternately training the discriminator and the generator. The discriminator is trained to correctly classify real and fake samples, while the generator aims to produce samples that can deceive the discriminator.
- The models are compiled with appropriate loss functions and optimizers.

### Results and Testing
- The GAN is trained over a specified number of epochs, and the progress is monitored by observing the discriminator and generator losses.
- The trained GAN can be used to generate artificial LWE samples, and a separate discriminator evaluates the authenticity of these generated samples.


