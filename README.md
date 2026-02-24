# CodeAlpha_HandwrittenCharacterRecognition


# CodeAlpha – Handwritten Character Recognition (Task 3)

This repository contains **Task 3** of the **CodeAlpha Machine Learning Internship**, focused on building an advanced **Handwritten Character Recognition system** using **Convolutional Neural Networks (CNNs)**.  
The project demonstrates a complete deep learning workflow from data preprocessing to model evaluation, visualization, and deployment readiness.

---

## 📌 Objective

The primary objective of this task is to **accurately recognize handwritten digits (0–9)** using image data and deep learning techniques.  
The task emphasizes not only high accuracy but also **model evaluation, interpretability, and performance comparison**, making it suitable for real-world applications.

---

## 📊 Dataset

- **Dataset:** MNIST Handwritten Digits
- **Training Samples:** 60,000
- **Testing Samples:** 10,000
- **Image Size:** 28 × 28 (Grayscale)
- **Source:** `tensorflow.keras.datasets.mnist`

### Preprocessing Steps
- Normalized pixel values to range [0, 1]
- Reshaped images to `(28, 28, 1)` for CNN input
- One-hot encoded class labels (10 classes)

---

## 🧠 Models Implemented

### 1️⃣ Baseline Neural Network
- Simple CNN architecture
- Used as a reference for performance comparison
- Faster training with reasonable accuracy

### 2️⃣ Advanced CNN Model
- Multiple convolution layers with Batch Normalization
- Dropout regularization to prevent overfitting
- Data augmentation for better generalization
- Achieves **very high test accuracy (~99.5%)**

---

## ⚙️ Training Configuration

- **Optimizer:** Adam  
- **Loss Function:** Categorical Crossentropy  
- **Evaluation Metric:** Accuracy  
- **Callbacks Used:**
  - EarlyStopping
  - ReduceLROnPlateau  

---

## 📈 Evaluation & Analysis

The models were evaluated using multiple advanced metrics and visualizations:

- ✔️ Test Accuracy comparison  
- ✔️ Confusion Matrix  
- ✔️ Classification Report (Precision, Recall, F1-Score)  
- ✔️ Multi-Class ROC-AUC Curves  
- ✔️ Training Time Comparison  
- ✔️ Model Parameters vs Accuracy analysis  

---

## 🔍 Model Interpretability

To understand **how the CNN makes predictions**, **Grad-CAM visualization** was applied.  
This highlights important regions of the digit image that influenced the model’s decision, improving transparency and trust.

---

## 🚀 Additional Enhancements

- Custom image prediction support (user-uploaded digits)
- Model scaling experiment (small vs large CNN)
- Saved trained model for reuse and deployment
- Streamlit-ready deployment code (optional extension)

---

## 🛠 Technologies Used

- Python  
- TensorFlow / Keras  
- NumPy  
- Matplotlib & Seaborn  
- Scikit-learn  
- Jupyter Notebook  

---

## 📁 Repository Structure

```text
CodeAlpha_HandwrittenCharacterRecognition/
│
├── Task3_HandwrittenCharacterRecognition.ipynb
├── Task3_Report.md
├── requirements.txt
├── Screenshots/
│   ├── confusion_matrix.png
│   ├── roc_curve.png
│   ├── gradcam.png
│   └── scaling_plot.png
└── README.md
