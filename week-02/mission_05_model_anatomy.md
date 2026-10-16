# Mission 5 — Understand the Anatomy of an ML Model

## 1. Algorithm, model, and parameters
- **Algorithm:** The procedure used to learn from data, such as a training method for linear regression.
- **Model:** The learned mapping from input features to an output.
- **Parameters:** Values adjusted during training. In a linear model, these can include weights and an intercept.

The algorithm is the learning procedure; the trained model is the result. Two models trained using the same algorithm can have different learned parameters because they were trained on different data.

## 2. Training and inference
- **Training:** The system uses training examples to adjust parameters. A loss or error measure indicates how far predictions are from target answers for the chosen objective. An optimisation procedure adjusts parameters to reduce that loss.
- **Inference:** After training, the model receives a new input and produces a prediction. Inference does not necessarily change the model parameters.

## 3. Flow diagram

```text
Define problem and target
          ↓
Collect and clean examples
          ↓
Split data into training / validation / test
          ↓
Choose algorithm and train on training data
          ↓
Use validation results to compare/tune choices
          ↓
Evaluate final selected model on test data
          ↓
Trained model
          ↓
New input → inference → prediction
          ↓
Monitor results and investigate errors
```

The diagram is simplified. In real projects, evaluation may reveal a data or modelling problem that requires returning to an earlier step.

## 4. Linear regression in plain English
Linear regression learns a relationship between input features and a numerical target. For example, it might learn how cell count and congestion relate to estimated delay. During training, it chooses model parameters that reduce a chosen error measure on the training data. For a new design run, the trained model uses its learned relationship to estimate delay.

A simple linear regression model can be written as:

`predicted delay = weight1 × cell count + weight2 × congestion + intercept`

This is a conceptual example, not a fitted formula. The weights and intercept must be learned from data. Real physical-design relationships may be nonlinear and affected by many other variables, so a simple linear model may not be sufficiently accurate.

## 5. What to remember
A prediction is an estimate, not proof. Model quality depends on the problem definition, data quality, training procedure, and evaluation on appropriate unseen examples.

## Sources
- Google, Introduction to Machine Learning: https://developers.google.com/machine-learning/intro-to-ml
- Google ML Crash Course — Linear regression: https://developers.google.com/machine-learning/crash-course/linear-regression
