# Mission 8 — Does This Problem Actually Need ML?

## Research Question

When should we use machine learning instead of a traditional rule-based approach?

## 1. Example Problem

Suppose a semiconductor engineering team wants to flag a design run whose estimated delay exceeds a fixed engineering limit.

A rule-based program can compare the measured or estimated delay against the known limit. Alternatively, a machine learning model could learn patterns from historical design features and labelled timing outcomes to estimate the likelihood of timing failure.

Both approaches can be useful, depending on the problem, available data, and engineering requirements.

## 2. Rule-Based Systems vs. Machine Learning

| Question | Rule-Based Solution | Possible ML Solution |
|---|---|---|
| How it works | Compares delay with a known threshold | Learns patterns from historical features and labelled timing outcomes |
| Data requirement | Requires a reliable measurement and a defined limit | Requires representative historical examples and trustworthy targets |
| Strength | Simple, transparent, and easy to test | Can combine multiple features and identify complex patterns |
| Limitation | May not capture complex relationships beyond its programmed rules | Can make incorrect predictions, overfit, or become less accurate as conditions change |
| Evaluation | Test rule correctness, units, and boundary conditions | Use suitable training, validation, and test procedures and relevant metrics |
| Failure mode | Incorrect threshold, measurement, or units | Poor data, leakage, bias, overfitting, or model drift |
| Maintenance | Update rules when requirements change | Monitor performance and retrain or update when justified |

## 3. When Is a Rule-Based Approach Better?

A rule-based approach may be preferable when:

- The requirements are clear and can be expressed as explicit rules.
- The engineering limit is authoritative and the measurement is reliable.
- The problem is stable and does not require learning complex patterns.
- Historical training data is unavailable or insufficient.
- Decisions need to be easy to inspect, explain, and test.
- A simple solution meets the requirements with acceptable risk.

**Example:** If an engineering specification states that a measured delay above a defined limit must be flagged, a direct comparison can perform that check without machine learning.

```python
if measured_delay > timing_limit:
    result = "Flag"
else:
    result = "Within limit"
```

This is an illustrative example. The actual threshold, units, and comparison conditions must come from the applicable engineering specification.

## 4. When Might Machine Learning Be Useful?

Machine learning may be useful when:

- Sufficient, relevant, and reliable data is available.
- Useful patterns are difficult to capture with manually written rules.
- Several features interact in ways that a simple threshold cannot represent.
- Predictions can help engineers prioritise investigations or experiments.
- Performance can be measured using appropriate metrics and unseen data.
- The expected benefit justifies the development, validation, monitoring, and maintenance costs.

**Example:** A model could learn from historical design characteristics and timing results to estimate which new design runs are more likely to experience timing problems.

However, the model must demonstrate useful performance compared with a simple baseline. A more complex model is not automatically a better solution.

## 5. Decision Process

Before choosing machine learning, follow these steps:

1. **Define the goal:** Decide whether the task is to apply a known rule, estimate a value, classify an outcome, or rank options.
2. **Check whether a rule is enough:** If a reliable measurement and authoritative threshold solve the problem, a rule may be the best option.
3. **Check data availability:** An ML approach needs relevant, representative data and trustworthy targets or another suitable learning signal.
4. **Define success:** Choose metrics that reflect engineering costs, such as missed failures, false alarms, or numerical prediction error.
5. **Assess consequences:** Determine what happens when the system is wrong and who will review its output.
6. **Compare against a baseline:** ML should demonstrate meaningful improvement over the simplest reasonable approach.
7. **Plan monitoring:** If the design environment or data changes, model performance may deteriorate.

## 6. Decision Checklist

Before implementing an ML solution, ask:

- Can a simple rule solve the problem adequately?
- Do we have enough relevant and reliable data?
- Can we define a measurable target or useful output?
- Can we evaluate the solution on appropriate unseen data?
- What are the consequences of false predictions?
- Can the solution be monitored and maintained?
- Will ML provide enough benefit to justify its complexity?

If a simple rule performs the task reliably, machine learning may not be necessary.

## 7. Connection to DFT (Design for Test)

In DFT and semiconductor testing, rule-based checks can handle known limits and explicit engineering requirements. Machine learning may complement those checks by identifying patterns in historical test data or estimating potential test problems.

For example:

- **Rule-based approach:** Flag a test measurement that exceeds a specified engineering limit.
- **Classification:** Predict whether a test run may pass or fail using labelled historical examples.
- **Anomaly detection:** Identify unusual test measurements that may require further investigation.

A rule can enforce a known requirement, while ML may help identify patterns that are harder to express through fixed rules.

These are illustrative applications, not experimentally verified results. Any ML model must be validated against appropriate data and engineering requirements. Predictions should support investigation and prioritisation rather than silently replace required test procedures or sign-off checks.

## Conclusion

Machine learning is not automatically better than a rule-based system. Rule-based methods are often appropriate for clear, stable requirements, while ML can be useful when reliable data contains patterns that are difficult to express manually.

The best solution is the simplest approach that meets the engineering objective with acceptable accuracy, reliability, and risk. ML should be selected because it provides demonstrated value, not merely because data is available.

## Sources

1. **Google for Developers — Problem Framing**  
   https://developers.google.com/machine-learning/problem-framing

2. **Google for Developers — Rules of Machine Learning**  
   https://developers.google.com/machine-learning/guides/rules-of-ml

3. **Google for Developers — Machine Learning Crash Course**  
   https://developers.google.com/machine-learning/crash-course

**Verification Note:** Review the relevant sections of these sources and record which concepts they support. The semiconductor examples are illustrative and do not represent measured engineering results.

