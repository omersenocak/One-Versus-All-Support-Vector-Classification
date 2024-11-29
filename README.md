# Multi-Class Classification Using One-Versus-All Support Vector Machines

## Project Overview
This project implements a one-versus-all support vector classification algorithm to classify a dataset of clothing images into five distinct categories: **T-shirt**, **Dress**, **Coat**, **Shirt**, and **Bag**. The approach leverages support vector machines (SVMs) with a Gaussian kernel, demonstrating the application of multi-class classification techniques.

---

## Dataset
The dataset consists of 5,000 grayscale images of clothing, each with a resolution of 28 × 28 pixels (784 features). Labels correspond to one of five clothing categories.

- **Training Data**: 1,000 samples (first 1,000 images)
- **Test Data**: 4,000 samples (remaining images)
- **Data Files**:
  - `images.csv`: Image data (features).
  - `labels.csv`: Image labels (1: T-shirt, 2: Dress, 3: Coat, 4: Shirt, 5: Bag).

<img width="471" alt="Images_sample" src="https://github.com/user-attachments/assets/c5c93c44-d70d-4fae-bd85-e45c96e29a23">

---

## Methodology
### 1. Preprocessing
- The dataset was divided into training and testing sets.
- Image features were standardized for SVM compatibility.

### 2. One-Versus-All Classification
- SVMs were trained for each class using a Gaussian kernel.
- Key parameters:
  - **C (Regularization Parameter)**: Controls the trade-off between maximizing the margin and minimizing classification error.
  - **s (Kernel Width)**: Determines the similarity metric in the Gaussian kernel.

### 3. Evaluation
- Confusion matrices were calculated for both training and test sets to assess model performance.
- Classification accuracy was measured for varying values of `C`.

---

## Results
### Confusion Matrices
#### Training Set
| Actual \ Predicted | T-shirt | Dress | Coat | Shirt | Bag |
|--------------------|---------|-------|------|-------|-----|
| **T-shirt**        | 207     | 1     | 0    | 9     | 0   |
| **Dress**          | 2       | 199   | 1    | 1     | 0   |
| **Coat**           | 0       | 1     | 204  | 6     | 0   |
| **Shirt**          | 0       | 1     | 4    | 185   | 1   |
| **Bag**            | 0       | 0     | 0    | 0     | 178 |

#### Test Set
| Actual \ Predicted | T-shirt | Dress | Coat | Shirt | Bag |
|--------------------|---------|-------|------|-------|-----|
| **T-shirt**        | 641     | 23    | 3    | 137   | 9   |
| **Dress**          | 43      | 714   | 27   | 40    | 4   |
| **Coat**           | 4       | 39    | 666  | 90    | 10  |
| **Shirt**          | 100     | 32    | 69   | 541   | 16  |
| **Bag**            | 12      | 2     | 6    | 15    | 757 |

<img width="661" alt="Results" src="https://github.com/user-attachments/assets/5f399bc8-20a9-4b66-83a3-6641b63bbc94">


### Accuracy
The classification accuracy was plotted as a function of `C` for both training and test sets, revealing the optimal trade-off for the regularization parameter.

---

## How to Run
### Prerequisites
- Python 3.x
- Required Libraries: `numpy`, `pandas`, `scikit-learn`, `matplotlib`

### Steps
1. Clone the repository.
2. Ensure `images.csv` and `labels.csv` are in the same directory as the script.
3. Run the Python script (`Notebook.ipynb`) in Jupyter Notebook or convert it into a `.py` file for execution.

---

## Key Learnings
- **One-Versus-All SVMs**: Demonstrated their efficacy in handling multi-class classification tasks.
- **Gaussian Kernel**: Showcased the importance of kernel choice in SVMs for complex data.
- **Parameter Tuning**: Highlighted the impact of hyperparameter optimization on model performance.

---

## Future Work
- Experiment with different kernels, such as polynomial or linear, to compare performance.
- Use advanced methods like Grid Search for hyperparameter tuning.
- Apply dimensionality reduction techniques (e.g., PCA) for potential performance improvements.

---

## Acknowledgments
- Dataset and inspiration derived from machine learning exercises.
- Gaussian kernel and SVM concepts based on foundational machine learning literature.
