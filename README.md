# Feature-Engineering-and-Data-preprocessing-Project-of-AI
This Python project analyzes 1,500 T20 cricket matches using EDA, statistical profiling, and K-Means clustering on overs played and run rate. Validated via the Elbow Method, $k=3$ optimal clusters cleanly segment match progression into early, middle, and late innings phases, built with Pandas, NumPy, SciPy, Scikit-learn, and Seaborn. 

# Supervised vs. Unsupervised Learning & K-Means Clustering
A comprehensive introduction to **Supervised vs. Unsupervised Machine Learning** paired with a practical implementation of the **K-Means Clustering** algorithm using Python and Scikit-Learn. This repository includes a Google Colab / Jupyter Notebook demonstrating unsupervised pattern discovery on a mock student lifestyle dataset.

---

## Table of Contents
- [Overview](#overview)
- [Core Concepts](#core-concepts)
  - [Supervised Learning](#supervised-learning)
  - [Unsupervised Learning](#unsupervised-learning)
  - [K-Means Clustering](#k-means-clustering)
- [Dataset Description](#dataset-description)
- [Repository Structure](#repository-structure)
- [Prerequisites & Installation](#prerequisites--installation)
- [Usage](#usage)
- [Workflow Breakdown](#workflow-breakdown)

---

## Overview

This project serves as an educational guide and lab exercise (`CSE 422 Lab 5`) designed to illustrate the foundational differences between supervised and unsupervised machine learning paradigms. It transitions from theoretical analogies into a hands-on exploratory data analysis (EDA) and clustering workflow using a two-feature dataset of student study and sleep habits.

---

## Core Concepts

### Supervised Learning
* **Analogy:** Learning with a teacher using labeled flashcards.
* **Mechanism:** The model is trained on labeled datasets where input features are mapped to known ground-truth outputs.
* **Goal:** Accurately predict labels or continuous values for new, unseen data.
* **Common Tasks:** 
  * *Classification* (e.g., distinguishing between images of cats and dogs).
  * *Regression* (e.g., predicting housing prices based on property features).

### Unsupervised Learning
* **Analogy:** Sorting a mixed box of LEGOs by color or shape without prior instructions.
* **Mechanism:** The model ingests unlabeled data and independently identifies underlying structures, similarities, or groupings.
* **Goal:** Discover hidden patterns, groupings, or relationships within raw data.
* **Common Tasks:**
  * *Clustering* (e.g., grouping similar images or behavioral profiles together).
  * *Dimensionality Reduction* (simplifying data while retaining essential variance).
  * *Association Rule Mining* (e.g., market basket analysis such as identifying items frequently purchased together).

### K-Means Clustering
K-Means is an unsupervised machine learning algorithm that partitions an unlabeled dataset into $K$ distinct clusters. It operates iteratively by:
1. Initializing $K$ cluster centers (**centroids**).
2. Assigning each data point to the nearest centroid.
3. Recalculating centroid positions based on assigned points until the clusters stabilize.

---

## Dataset Description

The notebook uses a mock dataset (`CSE 422 Lab 5 Mockup Data.csv`) representing student habits during a midterm week. It contains **50 records** and **3 columns** without predefined target labels:

| Column Name | Data Type | Description | Min | Max | Std Dev |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `ID` | Integer | Unique student identifier | `1` | `50` | `14.00` |
| `Hours Studied per day` | Float | Average daily hours spent studying | `0.5` | `11.0` | `2.66` |
| `Hours Slept per day` | Float | Average daily hours spent sleeping | `3.0` | `9.3` | `1.97` |

* **Dataset Source:** [Download Mockup CSV via Google Drive](https://drive.google.com/file/d/1jAUMdcBmkOfl27ad-m-J-FT75cZY3yIs/view?usp=drive_link)

---

## Repository Structure

```text
├── README.md                            # Project documentation
├── notebook.ipynb                       # Google Colab / Jupyter Notebook containing concepts, EDA, and K-Means setup
└── CSE 422 Lab 5 Mockup Data.csv        # Sample dataset (downloadable via the link above)
```

---

## Prerequisites & Installation

To run the notebook locally or in Google Colab, ensure you have **Python 3** along with the following libraries installed:

```bash
pip install pandas matplotlib scikit-learn jupyter
```

### Libraries Used
* `pandas` — Data loading, inspection, and manipulation.
* `matplotlib` — 2D scatter plot visualization.
* `scikit-learn` (`sklearn.cluster.KMeans`) — K-Means clustering implementation.

---

## Usage

### Option 1: Google Colab (Recommended)
1. Open the `.ipynb` notebook in [Google Colab](https://colab.research.google.com/).
2. Download `CSE 422 Lab 5 Mockup Data.csv` from the [Google Drive link](https://drive.google.com/file/d/1jAUMdcBmkOfl27ad-m-J-FT75cZY3yIs/view?usp=drive_link).
3. Upload the CSV file to your Colab session storage (e.g., `/content/sample_data/`).
4. Verify the file path in `pd.read_csv()` matches your uploaded file location and run all cells.

### Option 2: Local Jupyter Environment
1. Clone this repository and place `CSE 422 Lab 5 Mockup Data.csv` in your working directory.
2. Update the file path in the data-loading cell:
   ```python
   df = pd.read_csv("CSE 422 Lab 5 Mockup Data.csv")
   ```
3. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

---

## Workflow Breakdown

1. **Conceptual Overview:** Markdown explanations and visual diagrams contrasting supervised vs. unsupervised learning and illustrating K-Means centroid convergence.
2. **Environment Setup:** Importing `pandas`, `matplotlib.pyplot`, and `KMeans` from `sklearn.cluster`.
3. **Data Ingestion & Inspection:** Reading the CSV into a DataFrame (`df`), creating a backup copy (`df_copy`), and inspecting schema metadata via `df.columns` and `df.head(5)`.
4. **Exploratory Data Visualization:** Generating a 2D scatter plot comparing `Hours Slept per day` (X-axis) against `Hours Studied per day` (Y-axis) to visually inspect natural data groupings prior to clustering.
