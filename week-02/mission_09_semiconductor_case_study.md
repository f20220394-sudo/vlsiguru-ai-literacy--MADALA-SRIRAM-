# Mission 9 — Semiconductor Case Study: Predicting Physical-Design Timing

## Research Question

How can machine learning help predict whether a semiconductor design will meet its timing requirements during Physical Design?

## 1. Problem Statement

In semiconductor Physical Design, engineers need to determine whether a design satisfies its timing requirements. Detailed timing analysis and implementation runs can require significant computational resources, especially when engineers are exploring multiple design configurations.

Machine learning could use historical Physical Design data to predict whether a new design is likely to meet timing. This prediction could help engineers identify potentially problematic designs earlier and prioritise candidates for further investigation.

This is a proposed workflow, not a claim that a specific production team has deployed the exact system. The model would support engineering decisions rather than replace accurate timing analysis or sign-off.

## 2. Available Data

A hypothetical dataset could contain information collected from previous Physical Design runs.

| Feature | Description | Data Type |
|---|---|---|
| Cell count | Number of cells in the design | Numerical |
| Net count | Number of electrical connections or nets | Numerical |
| Estimated congestion | Estimate of routing congestion | Numerical |
| Placement utilisation | Proportion of placement area occupied by cells | Numerical |
| Clock frequency target | Required operating frequency | Numerical |
| Design configuration | Category describing the design setup | Categorical |
| Tool version | Version of the implementation tool | Categorical |
| Measured timing result | Timing result from trusted engineering analysis | Numerical |

The dataset must contain reliable, consistently defined measurements and representative examples from different design conditions. Features must be available at the time the prediction is made.

Design identifiers, post-implementation information, and other fields must be checked for data leakage. The model should not use information that would only become available after the intended prediction point.

## 3. Target Variable

The target variable is **Meets Timing**:

- **Yes:** The design satisfies the specified timing requirement.
- **No:** The design fails to satisfy the specified timing requirement.

The labels must be generated from trusted timing-analysis results using a clearly defined criterion, such as whether the relevant timing constraints are satisfied.

Because the output has two possible classes, this is a **binary classification** problem.

## 4. Machine Learning Task and Approach

**Learning approach:** Supervised learning.

**Task type:** Binary classification.

**Inputs:** Cell count, net count, estimated congestion, placement utilisation, clock frequency target, and other valid early-stage design features.

**Output:** A prediction indicating whether the design is likely to meet timing.

The model would learn patterns from historical examples in which the design features and actual timing outcomes are known. A simple classification model should be evaluated as a baseline before attempting more complex models.

For my DFT track, a related concept is predicting whether a design or test configuration may fail a defined check. However, timing prediction and DFT test-quality prediction are different engineering problems and should use their own appropriate data and target labels.

## 5. Proposed Workflow

1. Collect historical Physical Design features and trusted timing-analysis results.
2. Check missing values, inconsistent units, incorrect labels, and duplicate records.
3. Select features that would be available when the prediction is needed.
4. Split the dataset into training, validation, and test sets.
5. Where possible, separate data by design or block so closely related runs do not make test performance unrealistically easy.
6. Train a baseline classification model using the training set.
7. Use validation data to compare and tune candidate models.
8. Evaluate the selected model on previously unseen test cases.
9. Review major errors with Physical Design engineers.
10. Monitor performance when design conditions, libraries, constraints, or tool versions change.

The test set should represent the intended future use of the model, rather than merely containing additional runs that closely resemble the training data.

## 6. Evaluation Metrics

- **Recall for timing failures:** The proportion of actual timing-failing designs correctly identified by the model.
- **Precision for predicted timing failures:** The proportion of designs flagged as failures that actually fail timing.
- **Confusion matrix:** Shows true positives, true negatives, false positives, and false negatives.
- **Accuracy:** The proportion of all predictions that are correct.

Recall for timing failures may be particularly important because a false negative could cause a problematic design to be overlooked. However, low precision could create excessive false alarms and waste engineering time.

Evaluation should therefore consider the costs of different errors, not accuracy alone.

## 7. Expected Benefits

If the model proves sufficiently accurate on representative unseen cases, it could:

- Identify designs that may need early timing investigation.
- Help engineers prioritise candidate configurations.
- Provide an additional estimate during design-space exploration.
- Reveal patterns in historical data that deserve further engineering analysis.
- Potentially reduce unnecessary implementation runs, if the predictions are reliable enough for that purpose.

These are expected benefits, not measured results. They would need to be demonstrated through actual experiments and comparison with existing engineering methods.

## 8. Limitations and Risks

- **Poor data quality:** Incorrect measurements or labels may lead to unreliable predictions.
- **Data leakage:** Using information unavailable at prediction time may produce misleadingly strong test results.
- **Overfitting:** A model may perform well on training data but poorly on unseen designs.
- **Limited generalisation:** A model trained on one design family or tool version may not work well with another.
- **Changing conditions:** New libraries, process corners, constraints, and implementation tools may affect performance.
- **False predictions:** False negatives may hide timing problems, while false positives may waste engineering effort.
- **Misinterpreting correlations:** A feature associated with timing failure does not necessarily cause that failure.

The model should be used only within a clearly defined scope. Predictions must be reviewed appropriately, and required timing analysis and engineering sign-off must remain in place.

## 9. Conclusion

Machine learning could support semiconductor Physical Design by predicting whether a design is likely to meet its timing requirements using historical design data. Supervised binary classification is one possible approach because the target has two classes: timing met or timing not met.

The usefulness of the approach depends on data quality, representative examples, leakage-free evaluation, appropriate metrics, and engineering review. It should be treated as a decision-support tool rather than a replacement for trusted timing analysis or sign-off.

## Sources

1. Google for Developers — [Machine Learning Problem Framing](https://developers.google.com/machine-learning/problem-framing). Useful for defining the prediction target and success criteria.
2. Google for Developers — [Classification](https://developers.google.com/machine-learning/crash-course/classification). Explains classification concepts and evaluation.
3. Google for Developers — [Rules of ML](https://developers.google.com/machine-learning/guides/rules-of-ml). Provides practical guidance for building and evaluating machine learning systems.

**Evidence and verification note:** This report describes a proposed illustrative application. The dataset, workflow, and benefits have not been validated using actual semiconductor design runs. The sources above support the general ML methods; they do not establish that a particular semiconductor company has deployed this exact workflow. A semiconductor-specific research paper or official EDA technical publication should be added if the assignment requires primary evidence of a real application.

