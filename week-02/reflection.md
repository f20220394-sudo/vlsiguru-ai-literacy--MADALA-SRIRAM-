# Week 02 — Reflection

## 1. Which ML Concept Became Clearest, and What Helped?

The difference between training and inference became clearer to me. Training is the stage in which a machine learning model learns patterns and parameters from examples. Inference is when the trained model uses what it has learned to make predictions for new inputs.

Understanding the machine learning workflow helped me see how training and inference are connected but serve different purposes.

## 2. Which Two Concepts Are Easy to Confuse?

I initially found it easy to confuse a learning approach with a machine learning task type.

A learning approach describes how a model learns, such as supervised learning using labelled examples. A task type describes what the model needs to predict, such as a category in classification or a numerical value in regression.

For example, predicting whether a semiconductor design will meet timing is a binary classification task. If historical examples include the correct timing labels, supervised learning can be used.

## 3. What Is One Claim Checked Against a Reliable Source?

Google's Machine Learning Crash Course is a useful reference for understanding classification, training, and model evaluation.

**Verification note:** Before submission, I will open the relevant Google ML Crash Course page and check that the explanation matches my notes. I will record the specific concept and source page after checking it, rather than claiming verification without evidence.

Source: https://developers.google.com/machine-learning/crash-course

## 4. Which Lifecycle Stage Is Easiest to Underestimate, and Why?

I think data preparation and evaluation are easy to underestimate. A model may use a suitable algorithm but still produce unreliable predictions if the dataset contains incorrect labels, inconsistent units, missing values, or data leakage.

I also learned that good performance on training data does not guarantee good performance on unseen examples. Testing with representative data and choosing suitable evaluation metrics are important for understanding whether a model can generalise.

## 5. What Question Do I Want Answered Before Deep Learning?

I want to understand how neural-network layers and weights learn useful patterns from data. I also want to learn how engineers determine whether a model has learned meaningful relationships instead of memorising training examples.

## 6. What I Learned This Week

This week, I learned foundational machine learning concepts, including the relationship between artificial intelligence, machine learning, deep learning, generative AI, and large language models.

I learned how datasets, samples, features, and labels are used in machine learning. I also explored supervised, unsupervised, and reinforcement learning, along with the difference between algorithms, trained models, training, and inference.

Another important learning was how model performance can be evaluated using accuracy, precision, recall, and confusion matrices. These metrics help explain different kinds of prediction errors and why a single accuracy score may not tell the whole story.

## 7. Connection to My DFT Track

As a Design for Test (DFT) learner, I can see how machine learning might help analyse historical test results, identify unusual test patterns, or predict which designs may require further investigation.

For example, a proposed model could use historical test measurements and trusted pass/fail labels to estimate whether a new test result is likely to indicate a failure. Such a model would need representative data and careful evaluation, especially because false predictions could lead to unnecessary debugging or missed failures.

This is a possible application rather than a claim that I have built or validated such a model. Machine learning predictions should support engineering investigation, not replace established DFT checks, test procedures, or engineering judgement.

## 8. Challenges Faced

One challenge was distinguishing between similar machine learning concepts, especially an algorithm and a model, and training and inference.

Understanding evaluation metrics and the consequences of false positives and false negatives also required careful attention. Connecting these ideas to semiconductor engineering examples helped me understand why data quality and appropriate evaluation matter.

## 9. What I Want to Learn Next

I want to practise using Python to explore a dataset, clean the data, prepare features, train a basic machine learning model, and evaluate its predictions.

I also want to find and study a semiconductor-specific research paper or official technical publication that demonstrates a real application of machine learning in semiconductor testing or design.

## Conclusion

Week 02 helped me build a foundation in machine learning concepts, model evaluation, and risk awareness. I now have a clearer understanding that selecting an algorithm is only one part of developing a useful model. Data quality, appropriate evaluation, and generalisation to unseen cases are equally important.

As I continue learning DFT, I want to explore how machine learning can support semiconductor engineering while keeping predictions subject to proper verification and engineering review.

## References

- Google for Developers — Machine Learning Crash Course: https://developers.google.com/machine-learning/crash-course
- Google for Developers — Classification: https://developers.google.com/machine-learning/crash-course/classification



