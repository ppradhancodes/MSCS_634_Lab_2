# Lab 2: Classification Using KNN and RNN Algorithms  
**MSCS-634-B01 – Big Data and Data Mining**  
**Author: Prafulla Pradhan**

---

## Purpose

The purpose of this lab is to explore and compare the performance of two supervised classification algorithms:  
- **K-Nearest Neighbors (KNN)**  
- **Radius Neighbors (RNN)**  

Using the Wine dataset from `sklearn`, this lab demonstrates how parameter tuning (k-value and radius) influences classification accuracy. The goal is to develop an understanding of when each algorithm performs best and how model parameters affect outcomes.

---

## Key Insights

- **KNN Results**:
  - Accuracy was generally high and stable across different `k` values.
  - The best performance occurred at moderate `k` values (e.g., k = 5 or 11).
  - Smaller `k` (e.g., k=1) can lead to overfitting, while larger `k` values smooth the classification boundary.

- **RNN Results**:
  - Accuracy was more sensitive to the chosen `radius`.
  - Larger radii often caused many test samples to be predicted as outliers (label = -1), lowering accuracy.
  - Performance declined steadily as the radius increased beyond an optimal point.

- **Comparison**:
  - **KNN** outperformed **RNN** in this dataset due to more reliable neighbor inclusion and fewer classification gaps.
  - **RNN** could be useful in situations where density-based classification or local structures are important.

---

## Challenges and Decisions

- **Outlier Handling in RNN**:  
  When `RadiusNeighborsClassifier` couldn't find neighbors for some test points, it returned `-1` (outlier label). These cases were filtered out during accuracy calculations to prevent misleading results.

- **Parameter Selection**:  
  Radius values for RNN required tuning based on feature scale (raw numeric values). KNN was easier to tune and interpret.

- **Feature Scaling**:  
  The Wine dataset was used without scaling, as most features were already on comparable numeric ranges. In real-world scenarios, normalization may be necessary for distance-based models like KNN and RNN.

---

## Files in This Repository

- `Lab2_KNN_RNN.ipynb` — Main Jupyter Notebook with all code and plots.
- `README.md` — Overview of lab purpose, findings, and challenges.
- `Screenshots` - Screenshots of the outputs.

---

