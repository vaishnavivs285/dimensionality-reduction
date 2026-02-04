# Dimensionality Reduction on MNIST using PCA

## Overview
This project focuses on solving the problem of **high-dimensional data** using
**Principal Component Analysis (PCA)** and demonstrates how dimensionality
reduction improves visualization, efficiency, and clustering on image data.

The project uses the MNIST handwritten digits dataset, where each image is
represented by a large number of pixel features.

---

## Why Dimensionality Reduction?

In real-world datasets, especially image data, the number of features can be
very large. MNIST images contain **784 pixel features per image**, which leads to:

- High computational cost
- Slow model training
- Poor performance of distance-based algorithms
- Difficulty in visualization
- Curse of dimensionality

Dimensionality reduction helps by:
- Removing redundant and highly correlated features
- Preserving the most informative patterns
- Making data easier to visualize and analyze
- Improving efficiency of downstream algorithms

PCA is used in this project because it captures **maximum variance** while
reducing the number of dimensions.

---

## Dataset Used and Why This Dataset?

### Dataset: MNIST Handwritten Digits

- 70,000 grayscale images
- Digits from 0 to 9
- Image size: 28 × 28 pixels
- Each image flattened into 784 numerical features

### Why MNIST?

MNIST is ideal for a dimensionality reduction project because:

- It is **high-dimensional** (784 features per sample)
- Pixel values are highly **correlated**
- It represents real-world image data
- PCA benefits are clearly visible
- It allows both visualization and reconstruction analysis

This dataset clearly demonstrates the **curse of dimensionality** and how PCA
effectively addresses it.

---

## How the Dataset Was Loaded

The dataset was loaded using scikit-learn’s OpenML interface:

```python
from sklearn.datasets import fetch_openml

mnist = fetch_openml('mnist_784', version=1, as_frame=False)
X = mnist.data
y = mnist.target.astype(int)
```

This method:
- Avoids manual downloading
- Returns machine-learning-ready numerical data
- Ensures reproducibility using dataset versioning

---

## Why PCA Was Used?

Principal Component Analysis (PCA) was chosen because:

- It is an unsupervised dimensionality reduction technique
- It removes redundancy by finding orthogonal directions of maximum variance
- It reduces noise while preserving important structure
- It enables visualization of high-dimensional data
- It improves performance of distance-based algorithms

In this project:
- 784 dimensions were reduced to 40
- Around 90% of variance was retained
- Compression of ~95% was achieved

---

## Why KMeans Was Used?

KMeans clustering was applied **after PCA** to group similar digits.

Reasons for using KMeans:
- It is a simple and widely used clustering algorithm
- It works well on numerical data
- MNIST naturally contains 10 classes (digits 0–9)

Why PCA before KMeans?
- KMeans relies on distance calculations
- High-dimensional space distorts distance metrics
- PCA reduces noise and makes clustering more meaningful and efficient

---

## Why This Project Was Made?

This project was created to demonstrate:

- Practical handling of high-dimensional data
- Real-world application of PCA beyond theory
- How dimensionality reduction improves downstream tasks
- Visualization and interpretability of complex datasets
- Validation of PCA using reconstruction

---

## Who Benefits from This Project?

This project is useful for:

- Data Scientists dealing with high-dimensional data
- Machine Learning engineers working with images
- Anyone facing performance issues due to large feature spaces
- Learners trying to understand PCA conceptually and practically
- Teams optimizing computation and storage in ML pipelines

---

## Key Outcomes

- Reduced 784-dimensional image data to 40 dimensions
- Retained most of the important information
- Enabled 2D visualization of image data
- Demonstrated reconstruction quality
- Improved clustering performance using PCA + KMeans

---

## Technologies Used

- Python
- NumPy
- Matplotlib
- Scikit-learn

---

## Conclusion

This project demonstrates how dimensionality reduction using PCA helps manage
the curse of dimensionality in image data. By reducing redundant features while
preserving important patterns, PCA enables efficient visualization, clustering,
and analysis of complex datasets like MNIST.
