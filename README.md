# SVM_BreastCancerWisconsin

A SVM model trained on the [Breast Cancer Wisconsin (Diagnostic) Dataset](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data) predict the presence of breast cancer based on tumor cell features.

---

## About the dataset

The dataset contains features computed from digitized images of fine needle aspirate (FNA) samples of breast masses. These features describe various characteristics of the cell nuclei present in the images.
It consists of 569 samples with multiple tumor characteristics extracted from breast cancer cell nuclei. Each feature represents a statistical property (mean, standard error, or worst value) of measurements such as radius, texture, perimeter, area, smoothness, compactness, concavity, symmetry, and more.

### Columns:

- **id**: Unique sample identifier  
- **diagnosis**: Diagnosis of the tissue (M = malignant, B = benign)  
- **radius_mean**: Mean distance from the center to points on the perimeter  
- **texture_mean**: Standard deviation of gray-scale values  
- **perimeter_mean**: Mean size of the tumor’s core  
- **area_mean**: Mean area of the tumor  
- **smoothness_mean**: Mean of local variation in radius lengths  
- **compactness_mean**: Mean of (perimeter² / area - 1.0)  
- **concavity_mean**: Mean severity of concave portions of the contour  
- **concave points_mean**: Mean number of concave portions of the contour  


The first few rows of the dataset look like this:

| id       | diagnosis | radius_mean | texture_mean | perimeter_mean | area_mean | smoothness_mean | compactness_mean | concavity_mean | concave_points_mean |
|----------|-----------|--------------|---------------|-----------------|------------|------------------|------------------|----------------|----------------------|
| 842302   | M         | 17.99       | 10.38        | 122.80        | 1001.0    | 0.11840         | 0.27760         | 0.3001        | 0.14710             |
| 842517   | M         | 20.57       | 17.77        | 132.90        | 1326.0    | 0.08474         | 0.07864         | 0.0869        | 0.07017             |
| 84300903 | M         | 19.69       | 21.25        | 130.00        | 1203.0    | 0.10960         | 0.15990         | 0.1974        | 0.12790             |
| 84348301 | M         | 11.42       | 20.38        | 77.58         | 386.1     | 0.14250         | 0.28390         | 0.2414        | 0.10520             |
| 84358402 | M         | 20.29       | 14.34        | 135.10        | 1297.0    | 0.10030         | 0.13280         | 0.1980        | 0.10430             |

### Key insights from the summary statistics:

- The **mean radius** of tumors is approximately **14.13**, ranging from **6.98** to **28.11**.  
- The **mean area** shows considerable variation, with an average of **654.89** and a maximum of **2501.0**, indicating significant diversity in tumor sizes.  
- Features such as **concavity** and **compactness** exhibit high standard deviations, suggesting strong variability in tumor shape and structure.  
- The column **Unnamed: 32** contains only NaN values and can be safely removed from the dataset.

---

## About the Notebook

This notebook builds a Support Vector Machine (SVM) model to predict breast cancer, including all essential stages of the machine learning workflow like preprocessing and model optimization to evaluation and visualization.

The notebook is structured into the following sections:

- **Import libraries**  
- **Load the dataset**  
- **Transform the labels**  
- **Split the dataset into training and testing sets**  
- **Standardize the features**  
- **Use GridSearchCV to find optimal hyperparameters**  
- **Train and predict with the best model**  
- **Evaluate model performance using cross-validation**  
- **Evaluate performance with additional metrics**  
- **Visualize the confusion matrix**  
- **Visualize the ROC curve**  
- **Visualize the learning curve**

---

## Results

The optimized SVM model (`C=1`, `kernel='linear'`, `gamma='scale'`) delivered excellent predictive performance. It achieved a **cross-validation score of ~0.964** and a **test accuracy of 95.6%**, demonstrating strong generalization and robustness. The learning curve indicates stable training performance and steadily improving validation scores as more data is used. This suggests the model is neither overfitting nor underfitting and performs reliably across unseen data.

**Performance metrics:**

- **Precision:** 0.975 – The model produces very few false positives.  
- **ROC-AUC:** 0.996 – It distinguishes between malignant and benign cases almost perfectly.  
- **Recall:** 0.907 – A small number of positive cases were missed.  
- **F1-score:** 0.940 – Shows a strong balance between precision and recall.

---

Notebook created and trained on [Kaggle](https://www.kaggle.com) by Piyush Nagpal.


