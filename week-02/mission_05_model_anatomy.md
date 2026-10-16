# Mission 5 — Understand the Anatomy of an ML Model

## Research Question

What is the difference between an algorithm, a model, training, and inference?

## 1. Algorithm, Model, and Parameters

- **Algorithm:** An algorithm is a procedure or method used to learn patterns from data, such as the training method used for linear regression.
- **Model:** A model is the learned mapping from input features to an output. After training, it uses learned parameters to make predictions.
- **Parameters:** Parameters are values learned during training. In a linear model, they can include weights or coefficients and an intercept.

**Example:** Linear regression is a learning method. After it is trained on data, the resulting model contains learned coefficients and an intercept that can be used to predict a numerical value.

The algorithm is the learning procedure, while the trained model is the result. Two models trained using the same algorithm can have different learned parameters because they may use different training data.

## 2. Training and Inference

### Training

Training is the process of using data and a learning algorithm to fit a model's parameters. A loss or error measure evaluates how far predictions are from the target values. An optimisation procedure adjusts the parameters to reduce that loss.

### Inference

Inference is the process of applying a trained model to new input data to produce a prediction. Inference does not necessarily change the model's parameters.

**DFT example:**
- During training, a model learns patterns from historical semiconductor test measurements and their known outcomes.
- During inference, the trained model receives measurements from a new test run and predicts whether the run may pass or fail.

## 3. Machine Learning Workflow

```text
Define problem and target
          |
          v
Collect and prepare data
          |
          v
Split data into training,
validation, and test sets
          |
          v
Choose algorithm and train model
          |
          v
Use validation data to compare
and tune model choices
          |
          v
Evaluate the selected model
on the test set
          |
          v
      Trained model
          |
          v
       New input
          |
          v
       Inference
          |
          v
       Prediction
          |
          v
Monitor results and investigate errors
```

### Explanation of the Workflow

1. **Define the problem:** Decide what the model should predict and how success will be measured.
2. **Collect data:** Gather relevant examples, measurements, and outcomes.
3. **Prepare data:** Check data quality, handle missing values where appropriate, and prepare useful features.
4. **Split the data:** Use training data to fit the model, validation data to compare models or tune settings, and test data for final evaluation.
5. **Train the model:** Apply a learning algorithm to the training examples.
6. **Validate the model:** Compare candidate models and tune settings using validation results.
7. **Evaluate the selected model:** Assess its performance on suitable test data that was not used to fit or select the model.
8. **Perform inference:** Apply the trained model to new input data.
9. **Monitor results:** Investigate errors and check whether the model continues to perform reliably.

This is a simplified workflow. Evaluation may reveal a data or modelling problem that requires returning to an earlier step. The test set should not be repeatedly used for tuning because this can make the final evaluation overly optimistic.

## 4. Linear Regression in Plain English

Linear regression is a supervised learning method used to predict a numerical target.

For example, it could estimate a numerical semiconductor measurement from relevant input features.

A simple linear regression model can be written as:

\[
\hat{y} = w_1x_1 + b
\]

Where:

- \(\hat{y}\) is the predicted value.
- \(x_1\) is an input feature.
- \(w_1\) is the learned coefficient or weight.
- \(b\) is the learned intercept.

A conceptual model using two features could be written as:

\[
\widehat{\text{test time}} =
w_1(\text{test features}) + 
w_2(\text{scan complexity}) + b
\]

This is an illustrative formula, not a fitted model. The weights and intercept must be learned from training data.

### Training Example

Suppose we want to estimate semiconductor test execution time using historical test data.

The training dataset contains examples with test characteristics and measured execution times. The learning algorithm uses these examples to fit the model's coefficients and intercept by reducing a selected error measure.

The resulting model learns a relationship between the input features and the numerical target.

A real DFT problem may require several relevant features, and a simple linear model may not capture every relationship accurately.

### Inference Example

After training, suppose a new test configuration is provided to the model.

The model uses its learned parameters and the available input features to estimate the test execution time. A numerical prediction cannot be calculated unless the fitted model's parameters and input values are known.

The predicted time is an estimate, not a guaranteed result. It should be evaluated against actual measurements before being used for engineering decisions.

## 5. Why These Distinctions Matter

- An **algorithm** describes the learning procedure.
- A **model** contains the learned relationship used to make predictions.
- **Parameters** are values learned during training.
- **Training** fits the model using data.
- **Inference** applies the trained model to new inputs.
- **Evaluation** measures how well the model performs on appropriate data.

Understanding these distinctions helps engineers separate model development from model use and assess whether the predictions are reliable.

## 6. Connection to DFT (Design for Test)

Machine learning could potentially support DFT and semiconductor testing in several ways.

- A model could classify test runs as likely Pass or Fail using labelled historical data.
- A regression model could estimate test execution time from relevant test characteristics.
- An anomaly-detection system could flag unusual test measurements for further investigation.

During training, the model learns from historical examples. During inference, it applies what it has learned to new inputs.

These are potential applications, not claims that a particular model has been implemented or experimentally validated. Their usefulness depends on representative data, suitable evaluation metrics, and engineering validation. ML predictions should complement established test procedures and required engineering sign-off rather than replace them.

## Conclusion

An ML model is developed through a training process that uses an algorithm and data to learn parameters. Once trained, the model can perform inference on new inputs and generate predictions.

Understanding the complete workflow helps engineers interpret model outputs, evaluate performance, and recognise the limitations of machine learning in semiconductor engineering and DFT.

## Sources

1. **Google for Developers — Introduction to Machine Learning**  
   https://developers.google.com/machine-learning/intro-to-ml

2. **Google for Developers — Machine Learning Crash Course: Linear Regression**  
   https://developers.google.com/machine-learning/crash-course/linear-regression

3. **scikit-learn — Linear Models**  
   https://scikit-learn.org/stable/modules/linear_model.html

**Verification Note:** Review the relevant sections of these resources and record which concepts each source supports. The DFT examples are illustrative and do not represent measured or experimentally validated results.
