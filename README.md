
# CNN Experiments on CIFAR-10 Subset

## Overview

This project presents controlled experiments on a Convolutional Neural Network (CNN) trained on a subset of the CIFAR-10 dataset.

The objective of this study is not to achieve the highest possible accuracy, but to systematically analyze how architectural and training modifications influence performance, convergence behavior, and generalization.

---

## Dataset

* Dataset: CIFAR-10
* Image size: 32 × 32 × 3
* Number of classes: 10
* Classes: airplane, automobile, bird, cat, deer, dog, frog, horse, ship, truck

Preprocessing steps:

* Pixel normalization (scaled to [0,1])
* One-hot encoding of labels
* Optional data augmentation during training

---

## Experimental Setup

All experiments were conducted with:

* Optimizer: Adam
* Loss Function: Categorical Crossentropy
* Evaluation Metric: Accuracy
* Batch Size: 128
* Validation Split: 20%

Reproducibility was ensured by setting fixed random seeds.

---

## Model Architecture (Baseline)

The baseline CNN consists of:

* 3 Convolutional blocks

  * Conv2D (ReLU activation)
  * MaxPooling2D
* Fully connected dense layer
* Dropout for regularization
* Final Softmax output layer (10 classes)

The architecture is intentionally kept simple to allow clear interpretation of experimental modifications.

---

## Improvements Implemented

The following improvements were tested:

### 1. Data Augmentation

* Random horizontal flips
* Small random rotations
* Optional zoom/contrast adjustments

Purpose:
To improve generalization and reduce overfitting by increasing training data diversity.

---

### 2. Dropout Regularization

Applied after the dense layer to reduce overfitting.

Purpose:
To prevent co-adaptation of neurons and improve validation performance.

---

### 3. Training Callbacks

* EarlyStopping (monitored validation loss)
* ReduceLROnPlateau (adaptive learning rate reduction)

Purpose:
To stabilize training, avoid unnecessary overfitting, and optimize convergence.

---

## Results Summary

The introduction of data augmentation and regularization resulted in an approximate improvement of ~5% in test accuracy compared to the initial baseline.

Observed effects:

* Improved validation stability
* Reduced overfitting gap
* More consistent convergence behavior

---

## Key Observations

* Data augmentation contributed significantly to generalization.
* Regularization helped reduce divergence between training and validation performance.
* Learning rate scheduling improved late-stage convergence.
* Model complexity was intentionally limited to maintain interpretability.

---

## Limitations

* The architecture remains relatively shallow.
* No transfer learning or pretrained models were used.
* Hyperparameter search was limited to controlled experiments.

---

## Future Work

* Explore Batch Normalization integration.
* Compare Adam vs SGD with momentum.
* Evaluate deeper architectures while maintaining experimental control.
* Perform class-wise accuracy analysis.

---

## Conclusion

This study demonstrates that controlled architectural and training adjustments can produce meaningful improvements in model generalization.

Rather than focusing solely on accuracy maximization, emphasis was placed on understanding how specific modifications impact learning dynamics and real-world applicability.

---

If you’d like, I can also:

* Make a shorter version (if they prefer concise submissions)
* Or write a stronger “research-style” conclusion for higher impact
* Or help you draft Stage 2B (real-world impact reasoning) next

You’re doing this properly. Keep going.
