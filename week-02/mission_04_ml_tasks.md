# Mission 4 — Understand ML Task Types

## Research Question

What kinds of problems can machine learning solve?

## 1. Classification

**Definition:** Classification predicts a category or class from input data.

**Input:** Features describing an example.

**Output:** A predicted class or category.

**DFT Example:** Predicting whether a semiconductor test run will pass or fail based on historical test measurements.

**Why it fits:** The output belongs to one of two categories: Pass or Fail.

## 2. Regression

**Definition:** Regression predicts a numerical value.

**Input:** Features related to the quantity being predicted.

**Output:** A numerical value.

**DFT Example:** Predicting test execution time or estimating a numerical test measurement.

**Why it fits:** The output is numerical, such as execution time in seconds or a measured electrical value.

## 3. Clustering

**Definition:** Clustering groups examples based on similarities in their features without requiring predefined class labels.

**Input:** Feature measurements for multiple examples.

**Output:** Groups or clusters of similar examples.

**DFT Example:** Grouping semiconductor test runs with similar test measurements or failure characteristics.

**Why it fits:** The objective is to discover groups of similar runs rather than predict a known target.

## 4. Dimensionality Reduction

**Definition:** Dimensionality reduction represents data using fewer dimensions while preserving useful information as much as possible.

**Input:** Data containing many features.

**Output:** A lower-dimensional representation of the data.

**DFT Example:** Reducing a dataset containing many test measurements to a smaller number of dimensions to visualise patterns among test runs.

**Why it fits:** It can make complex datasets easier to explore and may support subsequent analysis.

## 5. Recommendation and Ranking

**Definition:** Recommendation suggests relevant items or options, while ranking orders candidates according to a scoring method or predicted relevance.

**Input:** Candidate options and relevant features, such as historical outcomes, test characteristics, or engineering constraints.

**Output:** Recommended options or an ordered list of candidates.

**DFT Example:** Ranking test cases for further investigation based on predicted failure relevance, test cost, or coverage objectives.

**Why it fits:** The objective is to prioritise options rather than simply assign a category or predict one numerical value.

## 6. Anomaly Detection

**Definition:** Anomaly detection identifies observations that differ significantly from expected patterns.

**Input:** Measurements or observations describing system behaviour.

**Output:** An anomaly score, flag, or list of unusual observations.

**DFT Example:** Flagging a test run with an unusual measurement pattern or an unexpected increase in test execution time.

**Why it fits:** The goal is to identify unusual behaviour that may require engineering investigation. Anomaly detection can use statistical methods, machine learning, or both.

## 7. Real-World Problem Comparison

| Problem | Input | Output | Task Type | Reason |
|---|---|---|---|---|
| Predict whether a test run passes | Test measurements and historical results | Pass or Fail | Classification | The output is a category. |
| Predict test execution time | Test characteristics and historical measurements | Time in seconds | Regression | The output is numerical. |
| Group similar test runs | Test measurements and failure characteristics | Clusters of runs | Clustering | The goal is to discover similarities. |
| Simplify a dataset containing many test measurements | High-dimensional test data | Lower-dimensional representation | Dimensionality reduction | The goal is to represent complex data more compactly. |
| Rank test cases for investigation | Candidate test cases and relevant characteristics | Ordered list of candidates | Recommendation / ranking | The goal is to prioritise options. |
| Detect an unusual test result | Historical and current test measurements | Anomaly flag or score | Anomaly detection | The goal is to identify unusual behaviour. |

## 8. How to Choose the Correct Task Type

The task type depends on the engineering question and the required output.

- If the output is a category, consider **classification**.
- If the output is a numerical value, consider **regression**.
- If the goal is to discover groups, consider **clustering**.
- If the data has many features and needs a compact representation, consider **dimensionality reduction**.
- If the goal is to suggest or prioritise options, consider **recommendation or ranking**.
- If the goal is to find unusual observations, consider **anomaly detection**.

The same dataset can support different task types depending on the problem being solved. For example, test data could be used to classify pass/fail outcomes, predict test execution time, or identify unusual measurements.

## 9. Connection to DFT (Design for Test)

Machine-learning task types could support different aspects of Design for Test and semiconductor testing.

- **Classification:** Predict whether a test run may pass or fail using labelled historical data.
- **Regression:** Estimate test execution time or another numerical test result.
- **Clustering:** Group test runs with similar measurement patterns.
- **Dimensionality reduction:** Simplify large test datasets to help engineers explore relationships.
- **Recommendation and ranking:** Prioritise test cases or results for further investigation using defined engineering objectives.
- **Anomaly detection:** Flag unusual test measurements or unexpected changes for investigation.

These are potential applications, not claims that a particular ML system has been implemented or experimentally validated. Their usefulness depends on data quality, appropriate evaluation, and engineering validation. ML predictions should complement established DFT procedures and required engineering sign-off rather than replace them.

## Conclusion

Machine learning includes several task types, each suited to a different objective. Classification predicts categories, regression predicts numerical values, clustering discovers groups, dimensionality reduction simplifies representations, recommendation and ranking prioritise options, and anomaly detection identifies unusual observations.

Identifying the required output first helps engineers choose an appropriate task type and evaluate whether the resulting solution is useful.

## Sources

1. **Google for Developers — Machine Learning Crash Course**  
   https://developers.google.com/machine-learning/crash-course

2. **IBM — What Is Machine Learning?**  
   https://www.ibm.com/think/topics/machine-learning

**Verification Note:** Review the relevant sections of these resources and record which concepts each source supports. The DFT examples are illustrative applications, not measured engineering results.

