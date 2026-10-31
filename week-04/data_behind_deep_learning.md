# Mission 1 – Data Behind Deep Learning

## 1. From Raw Data to Model Input

A digital image is made up of small units called pixels.

Each pixel contains numerical information representing brightness or colour.

For example:
- 0 represents black.
- 255 represents white in an 8-bit grayscale image.

A neural network cannot directly understand an image like a human. Therefore, the image is converted into numerical values.

**DFT Example:** Semiconductor inspection images can be converted into numerical pixel values to identify possible defects.

## 2. Data Preparation

Before training a neural network, data must be prepared.

- Resizing: Making images the same dimensions.
- Cleaning: Removing corrupted or unwanted images.
- Formatting: Converting data into a suitable format.
- Normalisation: Scaling numerical values into a consistent range, such as 0 to 1.

Data preparation helps the model learn more effectively.

## 3. Labels and Examples

An image is the input data, while a label is the correct answer.

Example:

| Image | Label |
|---|---|
| Defective chip image | Defect |
| Normal chip image | No Defect |

The labels should be checked and confirmed by engineers.

## 4. Data Quality

Data quality is important because a model learns from the examples provided.

Problems include:

1. Incorrect labels: The model learns wrong information.
2. Duplicate images: Evaluation may become misleading.
3. Noisy images: Defects may become difficult to identify.
4. Missing examples: The model may not learn rare defect types.

## 5. Representativeness and Imbalance

A dataset should contain different types of examples.

For example:

- 9,500 normal images.
- 500 defective images.

This dataset is imbalanced because normal images are much more common.

The model may predict most images as normal and still achieve high accuracy.

Therefore, engineers should also check precision, recall and F1-score.

## 6. Data Splitting

There are three important datasets:

**Training dataset:** Used to teach the model.

**Validation dataset:** Used to compare model settings and monitor performance.

**Testing dataset:** Used to evaluate the final model using unseen data.

The test dataset should not repeatedly guide training decisions because this can produce misleading evaluation results.

## Data Preparation Flow

Raw Images → Data Preparation → Labelled Dataset → Training → Trained Model → Prediction → Evaluation

## Two Data-Related Problems

1. Incorrect labels can teach the model wrong patterns.
2. Missing defect examples can cause the model to fail when identifying rare defects.

## Conclusion

Data preparation is an important part of deep learning. Good-quality data, correct labels and proper dataset splitting help build a more reliable model.
