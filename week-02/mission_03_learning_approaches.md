# Mission 3 — Understand the Main ML Approaches

## Research Question

How does a system learn when it has labels, no labels, or feedback from actions?

## 1. Comparison Table

| Approach | Training Signal | Typical Output | Example | One Limitation |
|---|---|---|---|---|
| Supervised learning | Inputs paired with target answers | Predicted label or number | Predict timing Pass/Fail from labelled design runs | Needs reliable labels and may not generalise to new designs |
| Unsupervised learning | Inputs without supplied target labels | Groups or structure in data | Cluster design runs with similar metrics | Groups may not have an obvious engineering meaning |
| Reinforcement learning | Feedback or reward after actions | A policy for choosing actions | Explore design choices with rewards based on PPA objectives | Reward design can be difficult, and exploration may be costly |
| Self-supervised learning | Training targets derived from the data itself | Learned representations or predictions | Predict a hidden section of a signal or the next part of a sequence | The self-generated task may not match the final engineering goal |

Self-supervised learning generates its own training signal from the data. It can learn without manually supplied labels, but unlike many traditional clustering approaches, it trains a model to predict targets constructed from the input itself. It is often treated as a distinct training approach in modern machine learning.

## 2. Process Diagrams

### Supervised Learning

```text
Labelled examples (features + correct answer)
                  |
                  v
               Training
                  |
                  v
             Trained model
                  |
                  v
       New example -> Prediction
```

### Unsupervised Learning

```text
Unlabelled examples
        |
        v
Pattern-finding algorithm
        |
        v
Groups / structure / representation
        |
        v
Engineer interprets the result
```

### Reinforcement Learning

```text
Agent chooses action
        |
        v
Environment changes
        |
        v
Reward or penalty
        |
        v
Agent adjusts its policy
        |
        +--------> Repeats interaction
```

### Self-Supervised Learning

```text
Raw data
   |
   v
Create a target from part of the data
   |
   v
Train model to predict the created target
   |
   v
Learn useful patterns or representations
```

## 3. When Might Each Approach Be Suitable?

- **Supervised learning:** When a meaningful target is available, such as a verified defect label or timing outcome.
- **Unsupervised learning:** When labels are absent and the goal is to explore patterns, unusual groups, or structure.
- **Reinforcement learning:** When actions affect a changing environment and there is a clear way to score long-term outcomes. It should be used carefully when experiments are expensive or risky.
- **Self-supervised learning:** When a large amount of raw data is available and useful training targets can be generated from the data itself.

## 4. Important Distinction: Learning Approach vs. Task Type

Learning approaches describe how a system receives its training signal. Task types describe what output or result is required.

For example:

- **Classification** predicts a category, such as Pass or Fail.
- **Regression** predicts a numerical value, such as estimated delay.
- **Clustering** groups similar examples.
- **Policy learning** develops a strategy for selecting actions.

Classification is commonly trained using supervised learning, while clustering is commonly associated with unsupervised learning. Reinforcement learning focuses on selecting actions to maximise cumulative reward. These concepts are related but are not interchangeable.

## 5. Connection to DFT (Design for Test)

Machine learning approaches could support semiconductor test engineering in different ways.

- **Supervised learning:** Predict whether a test run may fail using labelled historical test data.
- **Unsupervised learning:** Group test runs with similar characteristics or identify unusual measurement patterns.
- **Reinforcement learning:** Explore test-related decisions in a simulator using clearly defined objectives and constraints.
- **Self-supervised learning:** Learn representations from large collections of raw test measurements or signal sequences before using a smaller labelled dataset for a specific task.

These are potential applications, not claims that a particular model has been implemented or experimentally validated. Any model must be evaluated using representative data and appropriate metrics. Predictions should complement established testing, diagnosis, and engineering sign-off procedures.

## Conclusion

Supervised, unsupervised, reinforcement, and self-supervised learning differ in how they obtain their training signals and what they are designed to learn.

Understanding these differences helps engineers choose an appropriate approach based on the available data, the problem being solved, and the consequences of incorrect results.

In DFT, these approaches could support test-outcome prediction, test-data exploration, and analysis of raw measurement sequences. Their practical value must be demonstrated through appropriate validation rather than assumed.

## Sources

1. **Google for Developers — Introduction to Machine Learning**  
   https://developers.google.com/machine-learning/intro-to-ml

2. **IBM — What Is Machine Learning?**  
   https://www.ibm.com/think/topics/machine-learning

**Verification Note:** Review the relevant sections of these resources and record which claims they support. Confirm any additional claims about self-supervised learning using a suitable technical reference before stating that you verified them.

