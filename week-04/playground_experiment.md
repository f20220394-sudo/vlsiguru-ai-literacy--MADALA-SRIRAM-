# Mission 5 – Experiment and Observe

## Tool Used

TensorFlow Neural Network Playground

Website: https://playground.tensorflow.org/

## Objective

To understand whether increasing neural-network complexity always improves performance.

## Experiment Steps

1. Opened TensorFlow Playground.
2. Selected the Circle classification dataset.
3. Started with a neural network containing 2 hidden layers.
4. Observed the training behaviour and decision boundary.
5. Modified the network to contain 3 hidden layers.
6. Trained the modified network again.
7. Compared the training loss and test loss at epoch 1,500.

## Experiment Log

| Parameter | Starting Network | Modified Network |
|---|---|---|
| Dataset | Circle | Circle |
| Hidden layers | 2 | 3 |
| Number of neurons | Not recorded | Not recorded |
| Activation function | Not recorded | Not recorded |
| Epochs | 1,500 | 1,500 |
| Training loss | 0.000 | 0.000 |
| Test loss | 0.001 | 0.000 |
| Training behaviour | Loss decreased | Loss decreased |

*Note: Loss values are the displayed, rounded values from the Playground.*

## Questions and Answers

**1. What changed when you modified the network?**

I increased the number of hidden layers from 2 to 3. This increased the network's complexity and its ability to represent patterns.

**2. Did the more complex network always perform better?**

In my experiment, the 3-hidden-layer network showed a slightly lower displayed test loss (0.000) than the 2-hidden-layer network (0.001). However, one experiment does not prove that a deeper network will always perform better.

**3. What is the relationship between complexity and patterns?**

A complex network can learn more complicated patterns. However, unnecessary complexity can increase training time and may cause overfitting.

**4. Why is training performance not enough?**

A model may perform well on training data but poorly on unseen data. Therefore, test performance is also important.

**5. How is this different from real semiconductor inspection?**

TensorFlow Playground uses a simple artificial dataset. Real semiconductor inspection involves chip images, noise, process variations and rare defects. In DFT, machine learning can also support scan-test failure analysis.

**6. What evidence is required before practical use?**

- Good-quality labelled data.
- Independent test data.
- Precision and recall measurements.
- Evaluation of rare defects.
- Engineer verification.

## Conclusion

This experiment helped me understand that increasing the number of hidden layers can change neural-network performance. My modified network showed a lower displayed test loss, but more experiments are needed before concluding that a deeper network is always better.

I learned that model performance should be evaluated using unseen data, not only training loss.
