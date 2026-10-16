# Mission 7 — Understand Why ML Systems Fail

## Research Question

How can a machine learning model fail, and what risks should engineers consider before relying on its predictions?

## 1. Common ML Failure Modes

Machine learning models can fail when the training data is poor, the real-world data changes, or the model is used in situations different from those for which it was developed.

| Failure Mode | Likely Cause | Possible Impact |
|---|---|---|
| Poor data quality | Incorrect values, inconsistent formats, or measurement errors | The model may learn misleading patterns and produce unreliable predictions. |
| Unrepresentative training data | Training examples do not cover the range of real-world conditions | The model may perform poorly on unfamiliar cases. |
| Missing or noisy data | Important features are absent or measurements contain errors | Predictions may become less accurate or unstable. |
| Incorrect labels | Training examples have wrong target values | The model may learn incorrect relationships. |
| Data leakage | Information unavailable at prediction time is included in training features | Evaluation results may look unrealistically good. |
| Overfitting | The model learns noise or specific details of the training set | It may perform well on training data but poorly on new data. |
| Data or concept drift | Data characteristics or the relationship between features and outcomes changes | Model performance may decrease after deployment. |
| Lack of human oversight | Predictions are accepted without appropriate review | Incorrect predictions may lead to poor engineering decisions. |

## 2. Three Detailed Failure Scenarios

### Failure 1: Inconsistent Timing Data

**Scenario:** A model estimates timing from historical design runs, but some records use nanoseconds while others use picoseconds without conversion.

**Likely cause:** Inconsistent measurement units and inadequate data validation.

**Evidence to check:**
- Data dictionary and feature definitions.
- Original timing reports and data sources.
- Units used in each record.
- Suspicious values and outliers.

**Possible mitigation:**
- Standardise units during data ingestion.
- Validate units and reasonable value ranges.
- Document feature definitions and measurement conventions.
- Clean the data and repeat model evaluation.

### Failure 2: Data Leakage Produces an Unrealistically High Score

**Scenario:** A model predicts whether a design run passes timing, but one feature contains a post-sign-off status field that is only available after the outcome is known.

**Likely cause:** Data leakage. The model receives information that would not legitimately be available when the prediction must be made.

**Evidence to check:**
- Trace every feature to its source and timestamp.
- Determine when each feature becomes available.
- Check whether any feature directly or indirectly reveals the target.
- Compare evaluation results before and after removing suspicious features.

**Possible mitigation:**
- Remove features that leak future information.
- Split data according to the real prediction workflow.
- Evaluate the revised model using an untouched test set.
- Ensure preprocessing and feature selection do not use information from the test set.

### Failure 3: Performance Drops After a Tool or Design Change

**Scenario:** A model trained on older design runs performs poorly after a major EDA-tool version change or the introduction of a new class of designs.

**Likely cause:** The new data differs from the training data. This may involve data drift, changes in the relationship between features and outcomes, or both.

**Evidence to check:**
- Compare feature distributions before and after the change.
- Review design types, tool versions, libraries, and implementation settings.
- Compare failure rates and prediction errors where verified outcomes are available.
- Check whether performance differs across design categories.

**Possible mitigation:**
- Monitor input data and model performance.
- Collect representative new labelled examples.
- Retrain or recalibrate only when supported by evaluation.
- Keep engineering review in the loop, especially for high-impact decisions.

## 3. Other Risks and How to Detect Them

| Risk | How to Detect It | Possible Mitigation |
|---|---|---|
| Bias or unrepresentative data | Compare data coverage and performance across design types and operating conditions | Collect more representative examples and evaluate different groups separately |
| Missing values | Inspect feature completeness and missing-value patterns | Investigate why data is missing and use an appropriate handling method |
| Noisy measurements | Compare measurements with trusted sources and repeatability checks | Improve measurement quality and use suitable data-cleaning methods |
| Incorrect labels | Audit a sample of labels against trusted engineering records | Correct labels and establish reliable labelling procedures |
| Overfitting | Compare training, validation, and test performance | Simplify or regularise the model and improve evaluation practices |
| Human overreliance | Review whether predictions are accepted without checking their validity | Define review procedures, escalation rules, and limits on model use |

## 4. Semiconductor Engineering Example: DFT

Consider a hypothetical ML model intended to predict whether a semiconductor test run may pass or fail.

The model is trained using historical test data containing test measurements, test configuration details, and verified outcomes.

Several problems could affect its predictions:

1. **Poor data quality:** Test measurements may contain recording errors or inconsistent units.
2. **Unrepresentative data:** The training set may contain mostly one type of design or test configuration, while a new design differs significantly.
3. **Missing features:** Important test characteristics may be unavailable or recorded inconsistently.
4. **Data leakage:** A feature may reveal a test outcome that would not be known when the prediction is made.
5. **Incorrect labels:** A test run may be incorrectly labelled as Pass or Fail.
6. **Overfitting:** The model may perform well on historical examples but poorly on unseen test runs.
7. **Data drift:** Changes in test procedures, tools, devices, or operating conditions may make historical patterns less reliable.
8. **Lack of oversight:** Engineers may trust a prediction without investigating an unusual result or completing required testing.

These problems can lead to misleading predictions and cause engineers to overlook test runs that need further investigation.

## 5. Risk Reduction Strategies

Before relying on an ML model, engineers should:

- Validate and clean data before training.
- Standardise measurement units and feature definitions.
- Use representative datasets covering relevant design and test conditions.
- Check labels against trusted engineering records.
- Prevent data leakage by ensuring features are available at prediction time.
- Evaluate the model on suitable data that was not used for training or model selection.
- Monitor performance when tools, libraries, devices, or test conditions change.
- Investigate uncertain predictions and unexpected results.
- Keep qualified engineers involved in decisions that affect design quality or test sign-off.

No single strategy eliminates every failure mode. Risk reduction requires reliable data, careful evaluation, monitoring, and engineering judgement.

## 6. Why Human Oversight Matters

A machine learning prediction is an estimate based on learned patterns, not a guarantee of correctness.

The consequences of an incorrect prediction depend on the application. An inaccurate estimate used to prioritise experiments may be manageable. An incorrect prediction used to bypass required verification or sign-off can be expensive or dangerous.

Models should therefore be used only within a tested scope, with their limitations and failure cases understood. Predictions should support engineering decisions rather than automatically replace established verification procedures.

## Conclusion

Machine learning systems can fail because of poor data quality, unrepresentative samples, missing information, incorrect labels, data leakage, overfitting, changing conditions, and insufficient human oversight.

Engineers should identify these risks, evaluate models on appropriate data, monitor performance, and investigate unexpected results before relying on predictions in real-world semiconductor workflows.

For DFT, ML could potentially help analyse test data and prioritise unusual results, but its usefulness must be demonstrated through validation. Required test procedures and engineering sign-off must remain in place.

## Sources

1. **Google for Developers — Machine Learning Crash Course: Overfitting and Generalisation**  
   https://developers.google.com/machine-learning/crash-course/overfitting

2. **Google for Developers — Rules of Machine Learning**  
   https://developers.google.com/machine-learning/guides/rules-of-ml

3. **Google for Developers — Machine Learning Crash Course**  
   https://developers.google.com/machine-learning/crash-course

**Verification Note:** Review the relevant sections of these resources and record which concepts they support. The semiconductor scenarios are illustrative examples, not measurements from an actual design or test project.
