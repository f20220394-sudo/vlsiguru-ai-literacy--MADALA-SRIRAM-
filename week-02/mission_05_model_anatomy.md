# Mission 5 — Understand the Anatomy of an ML Model

## Research Question

What is the difference between an algorithm, a model, training, and inference?

## 1. Algorithm, Model, and Parameters

- **Algorithm:** An algorithm is a procedure or method used to learn patterns from data, such as the training method used for linear regression.
- **Model:** A model is the learned mapping from input features to an output. After training, it uses learned parameters to make predictions.
- **Parameters:** Parameters are values learned during training. In a linear model, they can include weights or coefficients and an intercept.

**Example:** Linear regression is a learning method. After it is trained on data, the resulting model contains learned coefficients and an intercept that can be used to predict a numerical value.

The algorithm is the learning procedure, while the trained model is the result. Two models trained using the same algorithm can have different learned parameters because they use different training data or settings.

## 2. Training and Inference

### Training

Training is the process of using data and a learning algorithm to fit a model's parameters. A loss or error measure evaluates predictions against target values for the chosen objective. An optimisation procedure adjusts parameters to reduce that loss.

### Inference

Inference is the process of applying a trained model to new input data to produce a prediction. Inference does not necessarily change the model's parameters.

**Example:**
- During training, a model learns relationships between historical semiconductor test measurements and known test outcomes.
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
Use validation results to
compare and tune choices
          |
          v
Evaluate selected model
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
2. **Collect data:** Gather relevant examples and measurements.
3. **Prepare data:** Check data quality, address missing values where appropriate, and prepare useful features.
4. **Split data:** Use training data to fit the model, validation data to compare or tune choices, and test data for final evaluation.
5. **Train the model:** Apply a learning algorithm to the training examples.
6. **Validate the model:** Compare candidate models and tune settings using validation results.
7. **Evaluate the selected model:** Assess its performance on suitable test data that was not used for fitting or model selection.
8. **Perform inference:** Apply the trained model to new input data.
9. **Monitor results:** Investigate errors and determine whether the model continues to perform reliably.

This is a simplified workflow. If evaluation reveals a data or modelling problem, the process may need to return to an earlier step. The test set should not be repeatedly used to tune the model because that can make the final evaluation overly optimistic.

## 4. Linear Regression in Plain English

Linear regression is a supervised learning method used to predict a numerical target.

For example, it could be used to estimate a numerical semiconductor test measurement from relevant input features.

A simple linear regression model can be written as:

\[
\hat{y} = w_1x_1 + b
\]

Where:

- \(\hat{y}\) is the predicted value.
- \(x_1\) is an input feature.
- \(w_1\) is the learned coefficient or weight.
- \(b\) is the learned intercept.

With two input features, a conceptual model might be:

\[
\widehat{\text{delay}} =
w_1(\text{cell count}) +
w_2(\text{congestion}) + b
\]

This formula is illustrative, not a fitted model. The weights and intercept must be learned from data.

### Training Example

Suppose we want to estimate a design run's delay using cell count as an input feature.

During training, the algorithm uses historical examples containing cell counts and measured delays to learn the coefficient and intercept. It adjusts the parameters to reduce a selected error measure.

A real semiconductor design may require additional features and a more suitable model because actual engineering relationships can be nonlinear and influenced by many factors.

### Inference Example

After training, suppose a new design run has a cell count of 15,000.

The trained model uses its learned coefficient and intercept to estimate the delay for that input. A numerical prediction cannot be calculated from the cell count alone unless the fitted model's parameters are known.

The predicted delay is an estimate, not a guaranteed timing result. Actual performance must be checked using appropriate engineering analysis.

## 5. Why These Distinctions Matter

- An **algorithm** describes the learning procedure.
- A **model** contains the learned relationship used to make predictions.
- **Parameters** are values learned during training.
- **Training** fits the model using data.
- **Inference** applies the trained model to new inputs.
- **Evaluation** measures how well the model performs on appropriate data.

Understanding these concepts helps engineers distinguish between developing a model, using it, and checking whether its predictions are reliable.

## 6. Connection to DFT (Design for Test)

Machine learning could potentially support DFT and semiconductor testing.

For example, a model could learn from historical test measurements and known outcomes during training. During inference, it could estimate whether a new test run may pass or flag a result that appears unusual.

Such predictions could support early investigation and prioritisation. Their usefulness depends on representative data, appropriate evaluation, and engineering validation. They should not replace established test procedures or required engineering sign-off.

## Conclusion

An ML model is developed through a training process that uses an algorithm and data to learn parameters. Once trained, the model can perform inference on new inputs and generate predictions.

Understanding the complete workflow helps engineers interpret predictions, evaluate model quality, and recognise the limitations of ML in semiconductor engineering.

## Sources

1. **Google for Developers — Introduction to Machine Learning**  
   https://developers.google.com/machine-learning/intro-to-ml

2. **Google for Developers — Machine Learning Crash Course: Linear Regression**  
   https://developers.google.com/machine-learning/crash-course/linear-regression

3. **scikit-learn — Linear Models**  
   https://scikit-learn.org/stable/modules/linear_model.html

**Verification Note:** Review the relevant sections of these resources and record which concepts each source supports. The semiconductor examples are illustrative and do not represent measured or experimentally validated results.

