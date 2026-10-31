# Mission 3 & 4 – Neural Networks and How They Learn

## Mission 3 – Open the Neural Network

### 1. Input Layer
Receives numerical information from the input data.

Example: Pixel values from a semiconductor inspection image.

### 2. Hidden Layers
Process information and identify useful patterns.

### 3. Output Layer
Produces the final prediction.

Example: Defect or No Defect.

### 4. Neurons
Neurons are small computational units that process information.

### 5. Weights
Weights determine the importance of different inputs.

### 6. Biases
Biases help adjust the output of a neuron.

### 7. Activation Functions
Activation functions help neural networks learn complex, non-linear relationships.

Examples:
- ReLU
- Sigmoid

### Example

An inspection image enters the network as numerical values. Hidden layers process the values and learn patterns. The output layer predicts whether the image may contain a defect.

The prediction is not automatically proof. Engineers must verify important results.

---

## Mission 4 – How Does a Neural Network Learn?

### 1. Forward Pass

Input data passes through the network and produces a prediction.

### 2. Loss Function

The loss function measures the difference between the prediction and the correct answer.

### 3. Optimisation

Optimisation updates the model parameters to reduce the loss.

### 4. Backpropagation

Backpropagation calculates how the parameters contributed to the prediction error.

The optimiser uses this information to update weights and biases.

### 5. Epoch

One epoch means one complete pass through the training dataset.

### 6. Training vs Inference

**Training:** The model learns from examples and updates its parameters.

**Inference:** The trained model uses its learned parameters to predict results for new inputs.

### 7. Generalisation

Generalisation means the model can perform well on data it has never seen before.

## DFT Example

Suppose a model predicts that a defective chip is normal.

During training:
1. The model makes a prediction.
2. The prediction is compared with the correct label.
3. Loss is calculated.
4. Backpropagation calculates parameter gradients.
5. The optimiser updates weights and biases.
6. The process repeats.

After training, engineers evaluate the model using unseen examples.

## Conclusion

Neural networks learn by repeatedly making predictions, calculating errors and updating their parameters. Proper evaluation is necessary to check whether the model works on new data.
