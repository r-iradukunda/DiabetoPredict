# Optimization Techniques in Machine Learning

## Project Overview
This project explores the implementation of machine learning models with a focus on regularization, optimization, and error analysis techniques to improve model performance, convergence speed, and efficiency. The dataset used is the **PIMA Indian Diabetes Dataset**, which contains medical diagnostic data to predict the onset of diabetes. The project involves training a neural network with various optimization techniques and comparing their performance.

## Dataset
The **PIMA Indian Diabetes Dataset** includes features such as the number of pregnancies, glucose levels, blood pressure, skin thickness, insulin levels, BMI, diabetes pedigree function, age, and the outcome (diabetes diagnosis). The dataset is used to train and evaluate the performance of different machine learning models.

---

## Findings

### Training Instances and Results

| Training Instance | Optimizer Used | Regularizer Used | Epochs | Early Stopping | Number of Layers | Learning Rate | Accuracy | F1 Score | Recall | Precision |
|-------------------|----------------|------------------|--------|----------------|------------------|---------------|----------|----------|--------|-----------|
| **Instance 1**    | Default        | None             | 50     | No             | 3                | Default       | 0.75     | 0.72     | 0.70   | 0.74      |
| **Instance 2**    | Adam           | L2               | 100    | Yes            | 4                | 0.001         | 0.78     | 0.75     | 0.73   | 0.77      |
| **Instance 3**    | RMSprop        | L1               | 80     | No             | 5                | 0.0001        | 0.77     | 0.74     | 0.72   | 0.76      |
| **Instance 4**    | Adam           | L1 and L2        | 120    | Yes            | 4                | 0.0005        | 0.79     | 0.76     | 0.74   | 0.78      |
| **Instance 5**    | RMSprop        | L2               | 150    | Yes            | 5                | 0.0001        | 0.80     | 0.77     | 0.75   | 0.79      |

---

## Discussion of Findings

### **Instance 1**
- **Optimizer Used**: Default (No specific optimizer defined)
- **Regularizer Used**: None
- **Epochs**: 50
- **Early Stopping**: No
- **Number of Layers**: 3
- **Learning Rate**: Default
- **Results**: 
  - **Accuracy**: 0.75
  - **F1 Score**: 0.72
  - **Recall**: 0.70
  - **Precision**: 0.74

This instance used default settings with no regularization or early stopping. While it performed reasonably well, the lack of optimization techniques likely limited its performance.

---

### **Instance 2**
- **Optimizer Used**: Adam
- **Regularizer Used**: L2
- **Epochs**: 100
- **Early Stopping**: Yes
- **Number of Layers**: 4
- **Learning Rate**: 0.001
- **Results**:
  - **Accuracy**: 0.78
  - **F1 Score**: 0.75
  - **Recall**: 0.73
  - **Precision**: 0.77

Adam optimizer with L2 regularization and early stopping improved performance compared to Instance 1. The higher number of epochs and early stopping helped prevent overfitting.

---

### **Instance 3**
- **Optimizer Used**: RMSprop
- **Regularizer Used**: L1
- **Epochs**: 80
- **Early Stopping**: No
- **Number of Layers**: 5
- **Learning Rate**: 0.0001
- **Results**:
  - **Accuracy**: 0.77
  - **F1 Score**: 0.74
  - **Recall**: 0.72
  - **Precision**: 0.76

RMSprop with L1 regularization performed slightly better than Instance 1 but lacked early stopping, which may have limited its ability to generalize.

---

### **Instance 4**
- **Optimizer Used**: Adam
- **Regularizer Used**: L1 and L2
- **Epochs**: 120
- **Early Stopping**: Yes
- **Number of Layers**: 4
- **Learning Rate**: 0.0005
- **Results**:
  - **Accuracy**: 0.79
  - **F1 Score**: 0.76
  - **Recall**: 0.74
  - **Precision**: 0.78

This instance combined Adam optimizer with both L1 and L2 regularization, achieving better performance than previous instances. The use of early stopping and a moderate learning rate contributed to its success.

---

### **Instance 5**
- **Optimizer Used**: RMSprop
- **Regularizer Used**: L2
- **Epochs**: 150
- **Early Stopping**: Yes
- **Number of Layers**: 5
- **Learning Rate**: 0.0001
- **Results**:
  - **Accuracy**: 0.80
  - **F1 Score**: 0.77
  - **Recall**: 0.75
  - **Precision**: 0.79

**Instance 5** achieved the highest performance across all metrics. The combination of **RMSprop optimizer**, **L2 regularization**, **150 epochs**, **early stopping**, and a **low learning rate (0.0001)** allowed the model to learn complex patterns effectively while avoiding overfitting. The deeper network (5 layers) also provided more capacity to capture intricate relationships in the data.

---

## Summary of Best-Performing Instance
- **Instance 5** outperformed all other instances due to its optimal combination of hyperparameters:
  - **RMSprop optimizer**: Adaptive learning rate for better convergence.
  - **L2 regularization**: Reduced overfitting by penalizing large weights.
  - **150 epochs**: Allowed the model to learn thoroughly.
  - **Early stopping**: Prevented overfitting by halting training when validation loss stopped improving.
  - **Low learning rate (0.0001)**: Enabled precise weight updates.
  - **5 layers**: Provided sufficient depth to capture complex patterns.

---

## Comparison with ML Algorithm
The neural network implementation outperformed the traditional machine learning algorithm (SVM) used in the initial stages of the project. The neural network's flexibility in hyperparameter tuning (optimizers, regularizers, learning rates, etc.) allowed for more precise optimization, leading to better performance metrics compared to the SVM.

### **Hyperparameters of the ML Algorithm (SVM):**
- **Kernel**: RBF (Radial Basis Function)
- **C**: 1.0 (Regularization parameter)
- **Gamma**: 'scale' (Kernel coefficient)

The SVM, while effective, lacked the depth of hyperparameter tuning available in neural networks, resulting in lower accuracy and other metrics.

---

## Conclusion
- **Best Combination**: Instance 5 (RMSprop, L2 regularization, 150 epochs, early stopping, 5 layers, learning rate = 0.0001) achieved the highest accuracy (0.80), F1 score (0.77), recall (0.75), and precision (0.79).
- **Neural Network vs. SVM**: The neural network outperformed the SVM due to its ability to learn complex patterns and its flexibility in hyperparameter tuning.
- **Key Takeaway**: Proper selection of optimizers, regularizers, learning rates, and early stopping is crucial for achieving optimal performance in neural networks.

- Presentation Video: https://youtu.be/d9xAXDzstbk
