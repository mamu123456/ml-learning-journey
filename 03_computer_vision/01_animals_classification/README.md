# Animal Classification: Cats vs Dogs

## Project Overview
This project focuses on building an image classification model to distinguish between cats and dogs using a small labeled dataset.

The goal was to understand the basics of computer vision workflows, including image preprocessing, building a Convolutional Neural Network (CNN), and applying transfer learning to improve performance.

---

## Dataset
- Source:  Kaggle [(Cats vs Dogs classification dataset)](https://www.kaggle.com/datasets/sureshmaheshwari021/cats-and-dogs)
- Classes:
  - Cats: 95 images
  - Dogs: 97 images

### Observations from Data Exploration
- Image dimensions vary significantly (width and height are inconsistent)
- All images are RGB (3 channels)
- File sizes range from ~26KB to ~1MB
- Aspect ratios are not consistent across images

These variations required preprocessing before training the models.

---

## Data Preprocessing
- Images were resized to a consistent input shape
- Data augmentation was applied to the training set only (not validation/test), including transformations such as rotation and flipping
- Dataset was split into training, validation, and test sets

---

## Models Implemented

### 1. Simple CNN
A basic Convolutional Neural Network was built from scratch with:
- Convolution + MaxPooling layers
- Flatten layer
- Fully connected (Dense) layers
- Dropout for regularization

This model was trained directly on the dataset without pre-trained features.

---

### 2. Transfer Learning (MobileNetV2)
To improve performance, transfer learning was applied using a pre-trained MobileNetV2 model.

- Pre-trained on ImageNet
- Used as a feature extractor
- Custom classification layers added on top
- Trained using:
  - Adam optimizer
  - Sparse categorical crossentropy loss
  - Accuracy metric
- Regularization techniques:
  - Early stopping
  - Learning rate reduction

---

## Model Performance Comparison

| Metric        | Simple CNN | Transfer Learning |
|--------------|-----------|------------------|
| Test Accuracy | 0.5588    | 0.9706           |
| Test Loss     | 0.6893    | 0.1268           |

### Key Observations
- The Simple CNN performed poorly, likely due to the small dataset size
- The Transfer Learning model significantly outperformed the CNN
- Transfer learning achieved strong and balanced performance across both classes

---

## Key Learning Points

- Building a CNN from scratch helped me understand the structure of convolutional models
- Small datasets are not sufficient for training deep models effectively from scratch
- Transfer learning is very powerful, especially when working with limited data
- Data augmentation helps improve model generalization

---

## Limitations

- The dataset size is very small, which limits generalization
- No deployment or real-world testing was performed
- Limited experimentation with different architectures and hyperparameters

---

## What I Would Improve Next

- Experiment with more advanced architectures and fine-tuning pre-trained layers
- Explore better data augmentation strategies
- Increase dataset size or use more diverse data
- Add clearer explanations and comments in the notebook for better readability

---

## Learning Reflection

This project helped me understand the practical difference between building a model from scratch and using transfer learning.

At the time, I was still developing my understanding of CNNs and relied partly on tutorials and external guidance to structure the models and training process.

Comparing the results of the two approaches made it clear how important pre-trained models are when working with small datasets.

---

## How to Run
1. Open the Jupyter Notebook
2. Install required dependencies (TensorFlow/Keras, NumPy, Matplotlib)
3. Run all cells to reproduce results

---

## Acknowledgment
Dataset sourced from Kaggle [(Cats vs Dogs classification dataset)](https://www.kaggle.com/datasets/sureshmaheshwari021/cats-and-dogs).
