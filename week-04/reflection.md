# Week 04 — Reflection

**Track:** VLSI – Design for Test (DFT)

## 1. What did I learn about data in deep learning?

I learned that data quality and preparation are important for training a reliable model. Features should represent useful information about the problem, and the data should be checked for missing values, inconsistencies and errors. In DFT, scan-test failure patterns and test results could be used as input data for machine learning. Good-quality data helps a model learn meaningful patterns.

## 2. Why are training and test data different?

Training data helps a model learn patterns, while test data helps evaluate how well it performs on examples it has not used during training. A model that performs well on training data may not generalise well to unseen data. Therefore, both are important when evaluating performance.

## 3. What did I understand about neural networks?

I learned that neural networks use interconnected neurons arranged in layers to learn relationships in data. Hidden layers and activation functions help a network learn patterns. However, adding more layers does not automatically make a model better.

## 4. What did I observe in TensorFlow Playground?

I compared a network with two hidden layers against one with three hidden layers using the Circle classification dataset. At epoch 1,500, both displayed a training loss of 0.000. The baseline displayed a test loss of 0.001, while the three-hidden-layer network displayed 0.000.

The experiment showed that both configurations learned the classification pattern. However, the displayed loss values were rounded, so this single comparison does not prove that a deeper network consistently performs better.

## 5. How can machine learning be useful in Design for Test (DFT)?

Machine learning could help engineers analyse scan-test failure patterns and identify possible scan-chain faults or failure categories. It could also help prioritise test failures for further investigation. For example, a model could analyse scan-test data and suggest possible intermittent faults. However, it would need to be trained and evaluated using representative, correctly labelled test data before being used in practical DFT applications.

## 6. Why is verification important in engineering applications?

Incorrect predictions can have practical consequences. A false negative could cause an actual scan-test failure to be overlooked, while a false positive could lead to unnecessary debugging work. Predictions should therefore be evaluated using suitable metrics such as precision, recall and F1-score, and reviewed by DFT engineers. Machine learning must not replace final test verification and engineering judgement.

## 7. What are my main takeaways and next steps?

My main takeaway is that model performance depends on data quality, model selection and reliable evaluation—not simply on increasing network complexity. I also learned that machine learning applications in DFT need careful verification.

My next steps are to strengthen my understanding of Python, neural networks and model evaluation, and to explore how machine learning can support scan-test failure diagnosis, fault detection and other DFT activities.
