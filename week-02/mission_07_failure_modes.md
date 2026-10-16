# Mission 7 — Understand Why ML Systems Fail

## Failure 1: Inconsistent timing data
**Scenario:** A model estimates timing from historical runs, but some rows use nanoseconds and others use picoseconds without conversion.

- **Likely cause:** Inconsistent units and poor data validation.
- **Evidence to check:** Data dictionary, source reports, unit distributions, and suspicious outliers.
- **Possible mitigation:** Standardise units at ingestion, validate ranges, document feature definitions, and rerun evaluation after cleaning.

## Failure 2: Data leakage creates an unrealistically high score
**Scenario:** A model predicts whether a run passes timing, but one feature contains a post-sign-off status field that is only available after the outcome is known.

- **Likely cause:** Data leakage: the model receives information that would not legitimately be available at prediction time.
- **Evidence to check:** Trace each feature to its source and timestamp; ask whether it exists before the prediction is made.
- **Possible mitigation:** Remove leaked features, split data according to the real prediction workflow, and repeat evaluation on an untouched test set.

## Failure 3: Performance drops after a tool or design change
**Scenario:** A model trained on older design runs performs poorly after a major EDA-tool version change or a new class of designs is introduced.

- **Likely cause:** The deployment data differs from the training data; this can be a form of data or concept drift.
- **Evidence to check:** Compare feature distributions, design types, tool versions, label rates, and error metrics before and after the change.
- **Possible mitigation:** Monitor performance, collect representative new labelled examples, retrain or recalibrate only after validation, and keep engineering review in the loop.

## Other risks
- **Bias / unrepresentative data:** Some design types or process conditions may be underrepresented, producing uneven performance.
- **Missing values:** A missing measurement may be informative; careless filling can distort patterns.
- **Label errors:** Incorrect Pass/Fail or defect labels teach the wrong relationship.
- **Noisy observations:** Measurement variation can make true patterns difficult to learn.
- **Human overreliance:** Engineers may accept a prediction without checking whether it is plausible or within the model's validated scope.

## Why human oversight matters
The consequences of a wrong prediction depend on the application. An inaccurate estimate used to prioritise experiments may be manageable; an incorrect prediction used to bypass required verification or sign-off can be dangerous or expensive. Models should be used only within a tested scope, with uncertainty and failure cases understood.

## Sources
- Google ML Crash Course — Overfitting and generalisation: https://developers.google.com/machine-learning/crash-course/overfitting
- Google, Rules of ML: https://developers.google.com/machine-learning/guides/rules-of-ml

