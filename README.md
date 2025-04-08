# finalyear_project
# 🧠 Superpixel-based GNN for Leukemia Image Classification

This project leverages Graph Neural Networks (GNN), particularly Graph Attention Networks (GAT), to classify leukemia images using superpixel-based segmentation. We convert leukemia cell images into graph representations and perform classification between **Acute Lymphoblastic Leukemia (ALL)** and **Healthy (HEM)** cells.

---

## 📁 Dataset

We use the **C-NMC dataset** consisting of thousands of microscopic blood smear images categorized into:
- `ALL`: Acute Lymphoblastic Leukemia
- `HEM`: Healthy cells

Directory structure:
![image](https://github.com/user-attachments/assets/ae79eb11-d8be-4940-8622-612dcbcc5557)

---

## ⚙️ Pipeline Overview

1. **Image Preprocessing**
   - Resize, normalize, and denoise images.
   
2. **Superpixel Segmentation**
   - Applied using SLIC with 50 segments per image.
   
3. **Graph Construction**
   - Nodes = superpixels
   - Edges = adjacent superpixels
   - Features = mean RGB and texture per superpixel

4. **EDA (Exploratory Data Analysis)**
   - Class distribution
   - Graph statistics (nodes, edges, degree)
   - Feature distributions (RGB, correlations)
   - t-SNE visualization of node features

5. **Model**
   - GNN model: Graph Attention Network (GAT)
   - Implemented using PyTorch Geometric
   - Train/test split with accuracy, precision, recall, F1-score, confusion matrix

6. **Deployment**
   - Web-based model demo (Flask or Streamlit)

---

## 📊 EDA Insights

- Class imbalance handled via stratified split.
- Node count per graph: 40–60
- RGB distributions are distinctive across ALL and HEM
- Features are moderately correlated
- t-SNE shows clear clustering for ALL vs HEM nodes

Sample visualizations:
- Histogram of node counts
- Heatmap of feature correlations
- t-SNE of node features

---

## 🧠 Model Performance

| Metric      | Score |
|-------------|-------|
| Accuracy    | 85  |
| Precision   | 85%   |
| Recall      | 85  |
| F1-score    | 85%   |

Confusion Matrix:
![confusion_matrix (2)](https://github.com/user-attachments/assets/d03f499a-cf5f-475b-a187-f0c6b73f8b9c)

