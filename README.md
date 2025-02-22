# CLPA: Clean-Label-Poisoning-Availability-Attacks
This is the implementation of AAAI-22 paper: https://www.aaai.org/AAAI22Papers/AAAI-3872.ZhaoB.pdf

Poisoning attacks are emerging threats to deep neural networks where the adversaries attempt to compromise the models by injecting malicious data points in the clean training data. Poisoning attacks target either the availability or integrity of a model. The availability attack aims to degrade the overall accuracy while the integrity attack causes misclassification only for specific instances without affecting the accuracy of clean data. Although clean-label integrity attacks are proven to be effective in recent studies, the feasibility of clean-label availability attacks remains unclear. This paper, for the first time, proposes a clean-label approach, CLPA, for the poisoning availability attack. We reveal that due to the intrinsic imperfection of classifiers, naturally misclassified inputs can be considered as a special type of poisoned data, which we refer to as "natural poisoned data". We then propose a two-phase generative adversarial net (GAN) based poisoned data generation framework along with a triplet loss function for synthesizing clean-label poisoned samples that locate in a similar distribution as natural poisoned data. The generated poisoned data are plausible to human perception and can also bypass the singular vector decomposition (SVD) based defense. We demonstrate the effectiveness of our approach on CIFAR-10 and ImageNet dataset over a variety type of models.

![image](https://user-images.githubusercontent.com/36553004/157361659-0dda060d-5b6e-4e10-a239-0f45c8f3c49f.png)


# Requirements
## Experiments using ImageNet dataset:

* PyTorch, version 1.0.1
* tqdm, numpy, scipy, and h5py
* The ImageNet training set

## Experiments using CIFAR-10 dataset:

* Keras 2.2.5
* Keras-Applications 1.0.8
* Keras-Preprocessing 1.1.0
* Tensorflow 1.15.0
* numpy 1.18.1
* matplotlib 2.2.2

# How to Run the Code
The current repository contains codes for the ImageNet experiments. We are cleaning up the codes for CIFAR-10 experiments and will update soon.
## A quick start to run experiments on the ImageNet dataset
To fine-tune a phase II GAN with the triplet loss, run:

```
sh scripts/utils/launch_MyBigGAN.sh
```
To generate a poisoned dataset, run the following:

```
sh scripts/utils/sample_finetune.sh
```
Please refer to the official repository of BigGAN if you want to play with different training settings or try different parameters.

# Useful links
Training BigGAN from scratch is time-consuming. You can download a pre-trained BigGAN model from the official repository of BigGAN at:

https://github.com/ajbrock/BigGAN-PyTorch

In our paper, we also used the pre-trained BigGAN model (138k G iters) for the ImageNet experiments.


# To Do List
- We will add codes for CIFAR10 experiments soon.

# Acknowledgements
This work is partially supported by the National Science Foundation Award 2047384.


# Citation
```
@inproceedings{DBLP:conf/aaai/ZhaoL22a,
  author    = {Bingyin Zhao and
               Yingjie Lao},
  title     = {{CLPA:} Clean-Label Poisoning Availability Attacks Using Generative
               Adversarial Nets},
  booktitle = {Thirty-Sixth {AAAI} Conference on Artificial Intelligence, {AAAI}
               2022, Thirty-Fourth Conference on Innovative Applications of Artificial
               Intelligence, {IAAI} 2022, The Twelveth Symposium on Educational Advances
               in Artificial Intelligence, {EAAI} 2022 Virtual Event, February 22
               - March 1, 2022},
  pages     = {9162--9170},
  publisher = {{AAAI} Press},
  year      = {2022}
}
```

