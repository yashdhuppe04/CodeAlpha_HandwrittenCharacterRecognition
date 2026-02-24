# Task 3 – Handwritten Digit Recognition using CNN (MNIST)

## 1. Objective

The objective of this task is to design, train, and evaluate a Convolutional Neural Network (CNN) for accurate classification of handwritten digits (0–9) using the MNIST dataset.  
The task emphasizes model performance, interpretability, and comparative analysis between a baseline and an advanced CNN architecture.

---

## 2. Dataset Description

- **Dataset:** MNIST handwritten digits (0–9)
- **Training samples:** 60,000
- **Testing samples:** 10,000
- **Image resolution:** 28 × 28 grayscale
- **Source:** `tensorflow.keras.datasets.mnist`

### Preprocessing Steps
- Normalization of pixel values to the range [0, 1]
- Reshaping images to `(28, 28, 1)` for CNN compatibility
- One-hot encoding of class labels (10 classes)

---

## 3. Model Architectures

### 3.1 Baseline CNN Model

A lightweight CNN used as a reference for performance comparison:

- Conv2D (32 filters, 3×3) + MaxPooling2D
- Flatten
- Dense (128 units, ReLU)
- Dense (10 units, Softmax)

This model is computationally efficient and achieves strong baseline accuracy on the MNIST dataset.

---

### 3.2 Advanced CNN Model

A deeper and regularized CNN designed for higher accuracy and improved generalization:

- Conv2D (32 filters, 3×3, ReLU)  
  + Batch Normalization + MaxPooling2D
- Conv2D (64 filters, 3×3, ReLU)  
  + Batch Normalization + MaxPooling2D
- Conv2D (128 filters, 3×3, ReLU)  
  + Batch Normalization
- Flatten
- Dense (128 units, ReLU) + Dropout (0.5)
- Dense (10 units, Softmax)

This architecture leverages depth, normalization, and dropout to reduce overfitting and enhance performance.

---

## 4. Training Configuration

- **Optimizer:** Adam
- **Loss Function:** Categorical Crossentropy
- **Evaluation Metric:** Accuracy

### Data Augmentation
- Rotation range: ±10°
- Width and height shift: 10%
- Zoom range: 10%

### Callbacks
- **EarlyStopping:** Monitors validation loss (patience = 3)
- **ReduceLROnPlateau:** Reduces learning rate on plateau (factor = 0.5, patience = 2)

---

## 5. Model Performance

### 5.1 Test Accuracy

| Model          | Test Accuracy |
|----------------|---------------|
| Baseline CNN   | ~0.984        |
| Advanced CNN   | ~0.996        |

The advanced CNN demonstrates a noticeable improvement in classification accuracy over the baseline model.

---

### 5.2 Confusion Matrix and Error Analysis

- A confusion matrix is generated to analyze class-wise prediction performance.
- Misclassified samples are visualized along with true and predicted labels to identify common error patterns.

---

## 6. ROC and AUC Evaluation

Since the model outputs class probabilities, ROC and AUC metrics are computed:

- **Per-class ROC curves** for digits 0–9
- **Micro-average ROC:** Aggregates all classes
- **Macro-average ROC:** Mean ROC across classes

This evaluation provides a threshold-independent assessment of the model’s discriminative capability.

---

## 7. Model Interpretability – Grad-CAM

To improve transparency and explainability:

- Grad-CAM is applied to selected test images.
- Heatmaps highlight image regions that most influenced the model’s predictions.

This helps verify that the CNN focuses on meaningful digit strokes rather than irrelevant background noise.

---

## 8. Efficiency and Scaling Analysis

### 8.1 Parameter Count vs Accuracy
- Total parameters are computed for each model.
- A scatter plot visualizes accuracy as a function of parameter count.
- An efficiency metric (accuracy per parameter) is discussed.

### 8.2 Training Time Comparison
- Approximate training times are recorded for both models.
- A bar chart illustrates the trade-off between accuracy and computational cost.

### 8.3 CNN Scaling Experiment (Optional)
- Small, Medium, and Large CNN variants are trained.
- Accuracy vs parameter count curves demonstrate scaling behavior.

---

## 9. Saved Artifacts

- **Notebook:** `Task3_MNIST_Digit_Recognition.ipynb`
- **Trained model:** `advanced_mnist_cnn_model.h5`
- **Visualizations:**
  - Confusion matrix
  - ROC curves
  - Grad-CAM heatmaps
  - Accuracy vs parameter plots

---

## 10. Conclusion

This task demonstrates an end-to-end deep learning workflow for image classification:

- Baseline and advanced CNN model design
- Robust evaluation using multiple metrics
- Model interpretability through Grad-CAM
- Practical analysis of performance vs complexity

The project is structured for reproducibility, clarity, and easy review, making it suitable for internship evaluation and further extension.