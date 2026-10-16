# Mission 2 — Understand Data: What Does an ML System Learn From?

## 1. Key Terms

- **Dataset:** A collection of examples used to study or train a model.
- **Sample / Observation:** One example or row in a dataset.
- **Feature:** An input value used by a model, such as measured delay or congestion.
- **Label / Target:** The answer the model is trained to predict, such as `Pass` or `Fail`.
- **Structured Data:** Data arranged in a defined format, such as rows and columns.
- **Unstructured Data:** Data such as images, free text, audio, or waveforms that do not naturally fit a simple table.
- **Numerical Feature:** A numerical value, such as power in milliwatts or delay in nanoseconds.
- **Categorical Feature:** A category, such as a process type, design family, or defect class.
- **Labelled Data:** Examples that include the target answer.
- **Unlabelled Data:** Examples that do not include a supplied target answer.

## 2. Illustrative Synthetic Dataset

The values below are invented only to demonstrate the concepts. They are not real chip measurements or experimentally verified results.

**Problem:** Predict whether a simplified semiconductor design run meets its timing target.

| Run | Cell Count (Thousands) | Congestion (%) | Estimated Delay (ns) | Timing Result (Target) |
| --- | ---------------------- | -------------- | -------------------- | ---------------------- |
| R1  | 20                     | 30             | 0.72                 | Pass                   |
| R2  | 25                     | 42             | 0.91                 | Pass                   |
| R3  | 31                     | 61             | 1.18                 | Fail                   |
| R4  | 18                     | 25             | 0.65                 | Pass                   |
| R5  | 35                     | 72             | 1.34                 | Fail                   |
| R6  | 29                     | 55             | 1.09                 | Fail                   |

### Identify the Dataset Components

- **Number of samples:** 6 design runs.
- **Features:** Cell count, congestion, and estimated delay.
- **Target / label:** Timing result.
- **Numerical features:** Cell count, congestion percentage, and estimated delay.
- **Categorical target:** Timing result, with two classes: Pass and Fail.
- **ML task:** Supervised binary classification.

A supervised classification model could learn patterns from the features and predict whether a design run is likely to meet its timing target.

However, six examples are far too few to train a dependable real-world model. The dataset is intended only for learning and explanation.

## 3. Structured and Unstructured Data

### Structured Data

Structured data is organised into a predefined format, such as rows and columns.

Examples in semiconductor engineering include:

- Design-run measurements.
- Cell counts and timing reports converted into tables.
- Manufacturing process settings.
- Semiconductor test results.

### Unstructured Data

Unstructured data does not naturally fit into a simple tabular structure.

Examples include:

- Microscope images of wafers.
- Engineering notes written in free text.
- Images of chip layouts.
- Raw signal waveforms before feature extraction.

Unstructured data can be processed to extract useful features before being used in an ML model.

### Numerical and Categorical Features

**Numerical features:**

- Delay in nanoseconds.
- Power in milliwatts.
- Temperature in degrees Celsius.
- Cell count.

**Categorical features:**

- Process corner.
- Tool version.
- Design block.
- Defect class.

Categorical features may need to be encoded into numerical representations before being used by many ML algorithms.

## 4. Data Preparation and Quality

Data preparation can include removing duplicate records, checking units, handling missing values, investigating outliers, and checking whether labels are consistent.

Missing values should not be filled arbitrarily. The method should be chosen based on why values are missing, the meaning of the measurement, and how the data will be used.

### Two Examples of Data-Quality Problems

**1. Incorrect labels**

If a timing run is labelled `Pass` even though it failed the required sign-off timing criterion, the model learns from an incorrect example. This can reduce prediction reliability.

**2. Inconsistent measurements**

If one tool records delay in picoseconds and another records it in nanoseconds without conversion, the model may learn misleading patterns because the values use different scales.

### Why More Data Is Not Always Better

A large dataset can still be inaccurate, duplicated, unrepresentative, or collected using inconsistent definitions.

Good ML development requires data that is reliable, relevant, representative, and consistent with the intended prediction task.

## 5. Data Splitting: Training, Validation, and Test Sets

Data is often separated into three subsets during model development.

- **Training set:** Used to fit the model.
- **Validation set:** Used to compare candidate models and tune model settings.
- **Test set:** Used for final evaluation on data that was not used to develop or select the model.

Keeping these sets separate helps provide a more realistic estimate of how the model may perform on unseen examples.

For semiconductor data, splitting must be done carefully. Runs from the same design, closely related configurations, or repeated measurements may be highly correlated. If near-duplicate runs appear in both training and test sets, evaluation results may be overly optimistic.

Where appropriate, splitting by design, project, or time period can provide a stronger evaluation of generalisation.

## 6. Data-Quality Checklist

Before training an ML model, ask the following questions:

- Are measurement units and definitions consistent?
- Are missing values identified and understood?
- Are labels checked against trusted outcomes?
- Do the examples represent the intended use case?
- Are duplicate or near-duplicate runs handled appropriately across data splits?
- Is every feature available at the time the model will make its prediction?
- Are there any features that indirectly reveal the target?
- Are the training, validation, and test sets kept separate?
- Does the dataset contain enough representative examples for the intended task?

This checklist helps identify data problems before they affect model training and evaluation.

## 7. Connection to DFT (Design for Test)

Machine learning could be explored in DFT for analysing historical semiconductor test results and identifying patterns associated with potential test failures.

### Possible Features

- **Scan-test coverage:** The percentage of modeled faults detected by the generated test patterns.
- **Test-pattern count:** The number of patterns generated for testing.
- **Test execution time:** The time required to execute a test.
- **Historical test information:** Previously available test and design characteristics.

### Possible Target

The target could be a binary label indicating whether a semiconductor test outcome is `Pass` or `Fail`.

### How ML Could Help

A supervised classification model could learn patterns from correctly labelled historical examples and estimate the likelihood of a test failure.

Its performance could be evaluated using:

- **Precision:** Of the cases predicted as failures, how many were actual failures?
- **Recall:** Of the actual failures, how many did the model identify?
- **F1-score:** A combined measure of precision and recall.
- **Confusion matrix:** A table showing correct and incorrect predictions for each class.

Recall can be particularly important when missing a genuine failure has significant consequences. The choice of evaluation metric should reflect the engineering objective and the cost of different errors.

### Limitations and Responsible Use

The dataset must be representative, labels must be reliable, and the features must be available at prediction time. Data leakage must be avoided, and model performance must be tested on suitable unseen data.

ML predictions may help engineers prioritise investigations and identify unusual patterns. However, they should not replace established test procedures, fault diagnosis, or engineering sign-off.

This is a proposed application, not the result of an experiment. No real semiconductor test data or trained model is claimed in this mission.

## 8. Conclusion

An ML system learns patterns from the examples and learning signals provided during development. Understanding datasets, samples, features, targets, data quality, and data splits is essential before selecting or training a model.

In semiconductor engineering, reliable data can support tasks such as timing prediction, test analysis, and failure investigation. However, model predictions are only useful when the underlying data is trustworthy and the model is evaluated appropriately.

For DFT, machine learning may complement established testing and diagnosis methods, but engineering validation and human oversight remain essential.

## Sources

1. **Google for Developers — Machine Learning Crash Course: Numerical Data**\
   [https://developers.google.com/machine-learning/crash-course/numerical-data](https://developers.google.com/machine-learning/crash-course/numerical-data)
2. **Google for Developers — Machine Learning Crash Course: Categorical Data**\
   [https://developers.google.com/machine-learning/crash-course/categorical-data](https://developers.google.com/machine-learning/crash-course/categorical-data)
3. **Google for Developers — Machine Learning Crash Course: Overfitting and Generalisation**\
   [https://developers.google.com/machine-learning/crash-course/overfitting](https://developers.google.com/machine-learning/crash-course/overfitting)

**Verification Note:** Review the relevant sections of these resources and confirm which concepts each source supports. Record only the verification you actually performed. The semiconductor datasets and applications in this mission are illustrative and are not evidence of an actual experiment.


