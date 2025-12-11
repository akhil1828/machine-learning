Why Equivalent Models Behave Differently: Sensitivity to Input Perturbations in Neural Networks
Overview

This repository accompanies a tutorial investigating why neural networks with identical architectures and near-identical test accuracy can behave differently when exposed to small input perturbations. Although standard evaluation metrics often suggest equivalence between such models, their robustness, prediction stability, and confidence can diverge significantly under noisy conditions.

The tutorial demonstrates this phenomenon using two neural networks trained with different random initialisations but identical architectures, datasets, and training procedures. Sensitivity to Gaussian noise is analysed to reveal behavioural differences not captured by conventional accuracy-based evaluation.

Objectives

The goals of this project are to:

Demonstrate that similar test accuracy does not imply similar model behaviour

Analyse sensitivity to input perturbations as a robustness metric

Quantify prediction instability using flip rates and confidence degradation

Highlight shortcomings of standard evaluation pipelines

Provide practical guidance for robustness-aware model assessment

Dataset

The experiments use the MNIST handwritten digit dataset, consisting of grayscale images of digits 0–9.

Training set: 60,000 samples

Test set: 10,000 samples

Each image is flattened into a 784-dimensional vector

Pixel values are normalised to the range [0,1]

The dataset is well-suited for controlled robustness studies due to its simplicity, interpretability, and widespread use in neural network research.

Methodology

Two multilayer perceptron models (Model A and Model B) are trained using:

Identical architectures

Identical training/validation/test splits

Identical optimisation settings

Different random initialisations

After training, both models are evaluated on clean test data and then under increasing levels of Gaussian noise added to the inputs.

The following robustness metrics are analysed:

Test accuracy under noise

Prediction flip rate relative to clean predictions

Average predictive confidence under perturbation

Experiments and Outputs

Running the provided Jupyter notebook reproduces all experimental results and figures used in the tutorial, including:

Training and validation loss curves for both models

Training and validation accuracy curves for both models

Accuracy vs. noise magnitude

Prediction flip rate vs. noise magnitude

Confidence vs. noise magnitude

These results illustrate how models with near-identical clean performance diverge meaningfully as noise increases.

Key Findings

Models with similar clean test accuracy can differ significantly in robustness

Prediction flip rates increase at different speeds across models

Confidence degradation under noise is model-dependent

Behavioural sensitivity reflects differences in optimisation trajectories, not architecture

Robustness evaluation reveals properties hidden by accuracy alone

Repository Contents


Jupyter notebook containing all experiments and evaluations

Generated figures used in the analysis

This README file

Open-source license

Reproducibility

All results presented in the tutorial are fully reproducible by running the provided notebook. No external data or proprietary dependencies are required beyond standard machine learning libraries.

Accessibility Considerations

To ensure accessibility and inclusivity:

Plots use high-contrast, colour-blind-safe palettes

Figures include descriptive captions suitable for alt-text

Tables do not rely on colour alone for interpretation

Content is structured with clear headings for screen readers

License

This project is released under the MIT License, allowing reuse, modification, and distribution with appropriate attribution.

References

All academic references used to inform the tutorial are listed in the final report and include peer-reviewed papers and authoritative textbooks on neural networks, robustness, and optimisation behaviour.
