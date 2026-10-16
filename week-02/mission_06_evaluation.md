# Mission 6 — Understand Evaluation and Generalisation

## 1. Data splits
- **Training set:** Used to fit the model's parameters.
- **Validation set:** Used during development to compare models or tune settings.
- **Test set:** Kept separate until final evaluation, to estimate performance on unseen examples.

If the test set is repeatedly used to make design choices, it stops being a clean final check. Data splitting must also prevent related or duplicate runs from leaking across sets when that would make the evaluation unrealistically easy.

## 2. Generalisation, overfitting, and underfitting
- **Generalisation:** The model performs usefully on new examples from the intended population.
- **Overfitting:** The model learns details or noise specific to its training data and performs worse on unseen data.
- **Underfitting:** The model is too limited or insufficiently trained to capture important patterns, so it performs poorly even on training data.

Training performance may be better than test performance because the model has already used the training examples to learn. Unseen examples provide a more realistic check of whether the learned pattern generalises.

## 3. Evaluation terms
- **Accuracy:** Fraction of predictions that are correct.
- **Precision:** Of the examples predicted positive, how many truly are positive?
- **Recall:** Of all actual positive examples, how many did the model identify?
- **False positive:** Model predicts positive when the actual class is negative.
- **False negative:** Model predicts negative when the actual class is positive.
- **Absolute error:** The magnitude of the difference between a numerical prediction and its true value.

The metric should match the cost of errors. In defect screening, missing a real defect may be much more serious than investigating a false alarm, so recall may be especially important. Precision is also useful because too many false alarms can waste engineering time.

## 4. Worked example: accuracy can mislead
Imagine a test dataset of 1,000 manufactured units:
- 990 units have no defect.
- 10 units have a defect.
- A model predicts “no defect” for every unit.

| Actual group | Correct predictions |
|---|---:|
| No defect | 990 |
| Defect | 0 |
| Total | 990 out of 1,000 |

Accuracy is `990 / 1000 = 99%`. This looks excellent, but the model finds **zero of the 10 defective units**. Its recall for the defect class is 0%. A high accuracy score hides the fact that the model is useless for finding defects.

For this situation, defect-class recall, precision, the confusion matrix, and possibly precision-recall analysis are more informative than accuracy alone. A simple baseline such as “always predict no defect” is valuable because it reveals whether the ML model provides real improvement over a trivial strategy.

## 5. Evaluation checklist
- Choose metrics before examining final test results.
- Compare against a simple baseline.
- Use validation data for development and test data for final evaluation.
- Check performance by important subsets, not only one overall score.
- Investigate false positives and false negatives.
- Test on data representative of real deployment.

## Sources
- Google ML Crash Course — Classification: https://developers.google.com/machine-learning/crash-course/classification
- Google ML Crash Course — Datasets, generalisation, and overfitting: https://developers.google.com/machine-learning/crash-course/overfitting

