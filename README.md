# Robust Membership Inference Attack (RMIA)

## Overview

This repository implements **my understanding** of the **Robust Membership Inference Attack (RMIA)**, an advanced privacy attack on machine learning models as described in recent academic research. The RMIA algorithm aims to infer whether a specific data point was part of the training set of a given target model, demonstrating vulnerabilities that can arise from model overfitting and insufficient privacy protection.


The repository includes:
- Training and evaluation of a **target model** using the CIFAR-10 dataset.
- Generation and training of **reference models** for use in the attack.
- Implementation of the **RMIA algorithm**, including likelihood ratio computation and attack evaluation metrics.

## Features
- **Target Model Training**: Train a ResNet18 model on a portion of the CIFAR-10 dataset.
- **Reference Models**: Generate and train multiple reference models to evaluate membership inference on the target model.
- **Likelihood Ratio Calculation**: Implement RMIA to compute membership likelihoods using reference models.
- **Attack Evaluation**: Measure the effectiveness of the attack using accuracy, precision, recall, and F1 score.

> Note: This code requires GPU support for efficient training of the target and reference models.

### Cloning the Repository

```sh
git clone https://github.com/yourusername/robust-membership-inference-attack.git
cd robust-membership-inference-attack
```

## Usage

### Step 1: Dataset Setup and Model Training
The Jupyter notebook `rmia-exp.ipynb` walks through the entire process, including:
- Preparing the CIFAR-10 dataset and splitting it into **training** and **shadow** sets for training the target and reference models.
- Training the **target model** using a ResNet18 architecture.
- Training **reference models** on disjoint subsets of the shadow dataset.

### Step 2: Performing RMIA
The notebook also contains the implementation of the **Robust Membership Inference Attack** (RMIA). This includes:
- Computing likelihood ratios for member and non-member data points.
- Evaluating the attack's effectiveness using metrics like accuracy, precision, recall, and F1 score.

### Step 3: Visualize Results
The notebook includes code to generate **ROC curves** and evaluate the effectiveness of the membership inference attack using **AUC scores**.

To run the notebook, use the following command:

```sh
jupyter notebook rmia-exp.ipynb
```

## Project Structure
- `rmia-exp.ipynb`: Jupyter notebook that contains a tutorial-style walkthrough of the entire RMIA implementation, including dataset preparation, model training, and attack demonstration.
- `checkpoints/`: Directory containing model checkpoints generated during training.

## Results
The RMIA attack is evaluated using a variety of metrics, including:
- **Accuracy**: Measures how accurately the attack classifies members and non-members.
- **Precision, Recall, F1 Score**: Provides detailed insights into the attack's performance.
- **ROC Curve & AUC**: Plots the Receiver Operating Characteristic (ROC) curve to demonstrate the effectiveness of the attack across different thresholds.

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## References
- Original paper: [Low-Cost High-Power Membership Inference Attacks]([https://arxiv.org/abs/example](https://arxiv.org/abs/2312.03262))

