# Machine Learning-Based PUF Analysis

This project was completed for the CS771: Introduction to Machine Learning course at IIT Kanpur. It explores the vulnerability of a Machine Learning-based Physical Unclonable Function (ML-PUF) to modeling attacks and interprets the resulting linear models.

## Project Overview

The project is divided into two main parts:
1.  **Breaking the ML-PUF:** We demonstrate that an ML-PUF can be successfully attacked and modeled using a single linear model. This involved creating a sophisticated feature map to handle the non-linear behavior of the PUF and then training a linear classifier to predict its responses. We also analyzed the performance of different solvers and the effect of various hyperparameters.
2.  **Model Interpretation:** We developed a method to interpret the learned linear model by reverse-engineering it to find a set of 256 non-negative delay values that could produce the observed behavior in a physical Arbiter PUF.

## Key Files

* `code/submit.py`: The Python script containing the core logic for the feature mapping (`my_map`), model training (`my_fit`), and model inversion (`my_decode`).
* `report/CS771_Assignment1.pdf`: The detailed project report that explains the theoretical background, mathematical derivations, and experimental results.

## How to Run

The primary functions in `submit.py` are designed to be used in a specific evaluation environment.

1.  `my_map(X)`: Takes an array of challenges `X` and transforms it into the high-dimensional feature space.
2.  `my_fit(X_train, y_train)`: Trains an SGD Classifier on the mapped training data.
3.  `my_decode(w)`: Takes a learned weight vector `w` and decodes it into four 64-dimensional delay vectors (p, q, r, s).

To test the code, you would need a dataset of challenge-response pairs (CRPs) from an ML-PUF.
