# Iris Flower Classification & Machine Learning

## 📌 Project Overview

This project explores the classic Iris flower dataset using multiple machine learning techniques.

The main goal is to classify Iris flowers into three species based on their sepal and petal measurements.

The project also explores feature scaling, feature selection, dimensionality reduction, hyperparameter tuning, cross-validation, and unsupervised clustering.

Complete ML workflow
• Dataset → EDA → Visualization → Preprocessing → Train/Test Split → Multiple Models → Evaluation →
Cross-Validation → Hyperparameter Tuning → PCA → Clustering → Neural Network → Final

## 📊 Dataset

The project uses the **Iris Species dataset**.

The dataset contains four numerical features:

* Sepal Length
* Sepal Width
* Petal Length
* Petal Width

Target classes:

* Iris-setosa
* Iris-versicolor
* Iris-virginica

## 🔍 Exploratory Data Analysis

The dataset was explored using:

* Pandas
* Matplotlib
* Seaborn

The analysis included:

* Dataset inspection
* Summary statistics
* Class distribution
* Feature distributions
* Feature relationships
* Correlation analysis
* Species comparisons

## 🤖 Machine Learning Models

The following classification algorithms were evaluated:

1. Decision Tree
2. Random Forest
3. Support Vector Machine (SVM)
4. Gaussian Naive Bayes
5. Perceptron
6. Multi-Layer Perceptron (MLP)

Model performance was compared using test-set accuracy and additional evaluation metrics.

## ⚙️ Feature Scaling

`StandardScaler` was used to standardize the numerical features.

Scaling was particularly useful for models such as:

* SVM
* Perceptron
* MLP

## 🔧 Hyperparameter Tuning

`GridSearchCV` was used to search for suitable hyperparameters for:

* Decision Tree
* Random Forest
* SVM

Cross-validation was used during the tuning process.

## 🔄 Cross-Validation

5-fold cross-validation was used to evaluate model performance across multiple training/validation splits.

A final SVM pipeline was created using:

```text
StandardScaler → SVM
```

Keeping preprocessing and the model together in a pipeline helps prevent preprocessing leakage during cross-validation.

## 🎯 Feature Selection

`SelectKBest` with ANOVA F-test (`f_classif`) was used to investigate the importance of individual features.

Different numbers of selected features were tested to study their effect on classification performance.

## 📉 PCA — Principal Component Analysis

PCA was used to reduce the four-dimensional feature space to two principal components.

This allowed the Iris dataset to be visualized in two dimensions while examining the amount of variance retained.

PCA was also combined with SVM to investigate classification using reduced-dimensional data.

## 🔵 K-Means Clustering

K-Means clustering was used as an unsupervised learning technique.

The following techniques were used to analyze the clusters:

* Elbow Method
* Silhouette Score
* PCA visualization
* Cluster vs. actual species comparison
* Adjusted Rand Index (ARI)

The actual species labels were not used to train K-Means.

They were only used afterward to evaluate how the discovered clusters corresponded to the known species.

## 💾 Model Saving

The final SVM pipeline was saved using Joblib:

```text
iris_svm_pipeline.pkl
```

The saved pipeline includes both:

```text
StandardScaler
      ↓
SVM
```

This allows the trained model to be loaded later without retraining it.

## 🗂️ Project Structure

```text
iris-machine-learning/
│
├── data/
│   └── Iris.csv
│
├── models/
│   └── iris_svm_pipeline.pkl
│
├── notebooks/
│   └── iris_ml_project.ipynb
│
├── README.md
├── requirements.txt
└── .gitignore
```

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Seaborn
* Scikit-learn
* Joblib
* Google Colab
* GitHub

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Open the notebook

Open:

```text
notebooks/iris_ml_project.ipynb
```

The notebook contains the complete analysis and machine learning workflow.

## 📈 Results

The project evaluated multiple machine learning algorithms and compared their performance.

The final SVM pipeline was evaluated using:

* Test-set accuracy
* Classification report
* Confusion matrix
* 5-fold cross-validation

### Model Comparison

The following models were evaluated on the test set:

| Model                | Test Accuracy |
| -------------------- | ------------: |
| Decision Tree        |        96.67% |
| Random Forest        |        90.00% |
| SVM                  |       100.00% |
| Gaussian Naive Bayes |        96.67% |
| Perceptron           |        76.67% |
| MLP                  |       100.00% |

### Cross-Validation — Decision Tree

The tuned Decision Tree was evaluated using 5-fold cross-validation:

| Metric                |     Result |
| --------------------- | ---------: |
| Mean CV Accuracy      | **94.17%** |
| CV Standard Deviation |  **2.04%** |
| Fold 1                |     91.67% |
| Fold 2                |     95.83% |
| Fold 3                |     95.83% |
| Fold 4                |     95.83% |
| Fold 5                |     91.67% |

The relatively small standard deviation indicates that the Decision Tree's validation accuracy was fairly consistent across these five folds.

### Final SVM Pipeline

The final classification pipeline combines:

```text
StandardScaler → Linear SVM
```

The pipeline achieved:

**Test Accuracy: 100.00%**

### Classification Report

| Class   | Precision | Recall | F1-Score |
| ------- | --------: | -----: | -------: |
| Class 0 |      1.00 |   1.00 |     1.00 |
| Class 1 |      1.00 |   1.00 |     1.00 |
| Class 2 |      1.00 |   1.00 |     1.00 |

### Confusion Matrix

```text
[[10  0  0]
 [ 0 10  0]
 [ 0  0 10]]
```

All 30 samples in the test set were classified correctly.

The model therefore made no classification errors on this particular test split.

### Additional Experiments

The project also investigated:

* Feature scaling
* Hyperparameter tuning using GridSearchCV
* 5-fold cross-validation
* Feature selection using SelectKBest
* Principal Component Analysis (PCA)
* PCA + SVM
* K-Means clustering
* Elbow method
* Silhouette score
* Adjusted Rand Index (ARI)

These experiments were used to understand how different preprocessing methods, supervised learning algorithms, dimensionality reduction techniques, and unsupervised learning methods affect the Iris classification problem.


The exact results are available in the notebook.

## 🎓 Key Learnings

Through this project, I practiced:

* Data preprocessing
* Exploratory data analysis
* Classification
* Model comparison
* Feature scaling
* Hyperparameter tuning
* Cross-validation
* Feature selection
* Dimensionality reduction
* Unsupervised learning
* Model persistence
* Building reproducible ML pipelines

## 👤 Author

**Your Name**

GitHub: [Your GitHub Profile](https://github.com/your-username)
