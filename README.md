This repository explores adversarial attacks and defense mechanisms in deep learning for image classification. It implements common attack methods and robust training strategies, followed by a comprehensive evaluation.

## Table of Contents

1.  [Project Overview](https://www.google.com/search?q=%23project-overview)
2.  [Models](https://www.google.com/search?q=%23models)
3.  [Dataset](https://www.google.com/search?q=%23dataset)
4.  [Adversarial Attacks](https://www.google.com/search?q=%23adversarial-attacks)
5.  [Defense Mechanisms](https://www.google.com/search?q=%23defense-mechanisms)
6.  [Evaluation](https://www.google.com/search?q=%23evaluation)
7.  [Usage](https://www.google.com/search?q=%23usage)

## Project Overview

This project investigates the vulnerability of image classification models to adversarial examples and implements defenses. It involves:

  * A **Student Model** for primary classification.
  * An **Ensemble Teacher Model** for robust knowledge generation.
  * **Adversarial Training** to improve teacher robustness.
  * **Adversarial Distillation** to transfer robustness to the student.
  * Extensive evaluation against various adversarial attacks.

## Models

  * **Simple Student Model**: Based on **ResNet-18**, adapted for binary classification.
  * **Ensemble Teacher Model**: An ensemble of **DenseNet-121**, **ResNet-50**, and **EfficientNet-B0**. Feature extractors are frozen, with learned weights combining outputs from adapted classification layers.

## Dataset

The **BreakHis dataset** is used for classification, expected to be located at `/content/drive/MyDrive/BreakHis_dataset_split/` with `train`, `validation`, and `test` splits. Standard image transformations (resize, normalize) are applied.

## Adversarial Attacks

  * **Fast Gradient Sign Method (FGSM)**: A one-step white-box attack generating perturbations based on the sign of the loss gradient.
  * **Projected Gradient Descent (PGD)**: An iterative white-box attack that applies multiple FGSM-like steps, projecting back to an epsilon-ball.
  * **Transfer Attacks**: Adversarial examples generated on one model are used to attack another model, testing cross-model vulnerability.

## Defense Mechanisms

  * **Adversarial Training**: The Teacher Model is trained on adversarial examples to enhance its robustness.
  * **Adversarial Distillation**: The Student Model learns from the robust Teacher Model's soft labels on adversarial examples, transferring robustness.

## Evaluation

Model performance and robustness are evaluated using:

  * **Metrics**: Accuracy, Precision, Recall, F1-Score, and Confusion Matrix.
  * **Scenarios**: Clean data, FGSM attacks (varying $\\epsilon$), PGD attacks (varying $\\epsilon$), and transfer attacks.
  * **Visualizations**: Accuracy vs. $\\epsilon$ plots for various attacks and confusion matrices for selected scenarios are generated.

## Usage

1.  **Clone Repository**: `git clone https://github.com/satyajithhb/Adversarial-attacks-fgsm-and-its-defense.git`
2.  **Dataset**: Place `BreakHis_dataset_split` in `/content/drive/MyDrive/BreakHis_dataset_split/`.
3.  **Run**: Execute the Python script (e.g., `step_7_1_testing_all_models.py`) in a suitable environment (e.g., Google Colab with GPU).
