# Membership Inference Attack Experiments

This repository contains our reproduction of two membership inference attack experiments from the following papers:

- Shokri et al., *Membership Inference Attacks Against Machine Learning Models*
- Salem et al., *ML-Leaks: Model and Data Independent Membership Inference Attacks and Defenses*

The goal of this project is to reproduce the experimental settings proposed in both papers, evaluate the attack performance, and compare our results with those reported in the original works.

## Overview

This project focuses on membership inference attacks in machine learning. We reproduce:

- the CIFAR-10 experiment from Shokri et al.;
- the Purchase-100 experiment from Salem et al.

For each experiment, we describe:
- the dataset used;
- the target model architecture;
- the attack model;
- the training procedure and hyperparameters;
- the obtained results and their analysis.

## Reproduced Experiments

### 1. Shokri et al. — CIFAR-10
We reproduce the experiment corresponding to Fig. 4 in the paper by Shokri et al.  
The target model is a convolutional neural network trained on CIFAR-10, and the attack is built using the shadow-model approach proposed in the paper.  
We study how the attack precision changes with different training set sizes.

### 2. Salem et al. — Purchase-100
We reproduce the Purchase-100 experiment from Salem et al.  
The Purchase dataset is transformed into a classification problem with 100 classes, and the membership inference attack is evaluated using the setup described in the paper.


## Methods

### Target Model
For each experiment, a target model is trained on a subset of the dataset.  
The target model is treated as a black box: only its outputs are used by the attacker.

### Shadow Models
Shadow models are trained on auxiliary data drawn from the same distribution as the target training data.  
Their outputs are used to build the attack dataset.

### Attack Model
The attack model learns to distinguish between member and non-member examples based on the target model’s output probabilities.

## Results

The repository includes the results obtained from our implementations and their comparison with the original papers.  
We report precision, recall, and class-wise attack performance when applicable.

## Requirements

- Python 3.x
- PyTorch
- NumPy
- scikit-learn
- LightGBM
- Matplotlib
- torchvision

## How to Run

1. Install the required dependencies.
2. Download the datasets.
3. Run the scripts for the desired experiment.
4. Inspect the generated plots and saved results.

## References

- Shokri, R., Stronati, M., Song, C., and Shmatikov, V. *Membership Inference Attacks Against Machine Learning Models*.
- Salem, A., Zhang, Y., Humbert, M., Berrang, P., Fritz, M., and Backes, M. *ML-Leaks: Model and Data Independent Membership Inference Attacks and Defenses*.