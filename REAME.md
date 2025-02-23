# Diabetes Prediction Using Machine Learning Techniques

## Problem Statement

Diabetes is a chronic disease that requires early detection to prevent severe complications. This project applies machine learning techniques to predict diabetes using patient data, leveraging both classical ML algorithms and deep learning models with different optimization techniques.

## Dataset Used

The dataset used is the **PIMA Indian Diabetes Dataset**, which contains diagnostic variables collected from female patients. Features include glucose levels, blood pressure, insulin levels, BMI, age, and other health-related metrics.

## Model Comparison Table

| **Training Instance** | **Optimizer Used** | **Regularizer Used** | **Epochs** | **Early Stopping** | **Layers** | **Learning Rate** | **Dropout** | **Accuracy** | **F1-Score** | **Recall** | **Precision** |
|------------------------|--------------------|----------------------|------------|--------------------|------------|-------------------|-------------|--------------|--------------|------------|---------------|
| **Instance 1**         | Default (Adam)     | None                 | 50         | No                 | 3          | Default           | None        | 82.1%        | 0.78         | 0.76         | 0.80          |
| **Instance 2**         | Adam               | L2                   | 100        | Yes                | 3          | 0.0001            | 0.3         | 85.3%        | 0.81         | 0.79         | 0.84          |
| **Instance 3**         | RMSprop            | L1                   | 120        | Yes                | 4          | 0.001             | 0.2         | 83.5%        | 0.79         | 0.78         | 0.81          |
| **Instance 4**         | Adamax             | L2                   | 130        | Yes                | 3          | 0.001             | 0.2         | 84.7%        | 0.80         | 0.78         | 0.83          |
| **Instance 5**         | SGD                | L2                   | 130        | Yes                | 4          | 0.001             | 0.4         | 80.5%        | 0.75         | 0.74         | 0.77          |

## Discussion of Findings

1. **Instance 1** (No optimization) had the lowest performance, showing that optimization significantly improves results.
2. **Instance 2** (Adam + L2 Regularization) performed the best in terms of accuracy and F1-score.
3. **Instance 5** (SGD with L2 and 0.4 dropout) underperformed, indicating that excessive dropout may negatively impact training.
4. **Instance 3 & 4** had similar performance but Adam-based optimizers showed more stability in convergence.

## Summary of Best Model

The best-performing model was **Instance 2 (Adam + L2 Regularization, 100 epochs, 0.0001 learning rate, and 0.3 dropout)**. It achieved the highest accuracy and balance between recall and precision.

## ML Algorithm vs. Neural Network

- **Support Vector Machine (SVM)** with tuned hyperparameters achieved an accuracy of **83.2%**, which is competitive with neural networks.
- The **optimized neural network outperformed SVM**, especially with proper tuning of **learning rates, dropout, and regularization**.
- The best hyperparameters for classical ML (SVM) were **C=10, kernel='rbf', gamma=0.1**.

## Conclusion

This study shows that **deep learning with proper optimization outperforms traditional ML methods** for diabetes prediction. However, classical ML models like **SVM remain viable choices**, particularly when computational efficiency is a concern. The best performance was achieved using an Adam optimizer with L2 regularization and early stopping.