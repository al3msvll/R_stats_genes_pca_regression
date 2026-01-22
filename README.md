# 🧬 Multivariate Analysis of Obesity-Related Gene Expression

**Master in Bioinformatics – R statistics project **
**Group 8**
**Date:** January 2026

---

## 📌 Project Overview

This repository contains the complete multivariate statistical analysis performed for *Activity 3* of the Master in Bioinformatics. The objective of this work is to explore **patterns of gene expression associated with obesity-related phenotypes** using unsupervised learning techniques.

The analysis integrates:

* Data preprocessing and quality control
* Normalization assessment
* Principal Component Analysis (PCA)
* Clustering of genes and individuals
* Visualization of gene contributions
* Biological interpretation in relation to BMI (IMC)

All analyses were performed in **R**, following reproducible and transparent data-science practices.

---

## 🧠 Biological Context

The dataset contains expression values of genes previously associated with:

* Energy balance
* Appetite regulation
* Hypothalamic signaling
* Obesity risk (e.g. *LEP, LEPR, MC4R, POMC, FTO, ADCY3, PCSK1*)

In addition, anthropometric variables such as **BMI (IMC)** were used to explore how molecular patterns relate to phenotypic stratification.

---

## 📂 Repository Structure

```
.
├── data/
│   └── data_simpson.csv
│
├── scripts/
│   └── analysis_activity3.R
│
├── results/
│   ├── PCA_plots/
│   ├── clustering/
│   ├── heatmaps/
│   └── figures/
│
├── report/
│   ├── actv3_g8.html
│   └── actv3_g8.docx
│
└── README.md
```

---

## 🔬 Analysis Workflow

### 1️⃣ Data Preparation and Cleaning

* Selection of gene-expression variables
* Removal of missing values (NA)
* Verification of zero-variance genes

✔ No missing values or zero-variance genes were detected

---

### 2️⃣ Normality Assessment

A **Shapiro–Wilk test** was applied to each gene:

* Null hypothesis: data follow a normal distribution
* Result: **all genes showed non-normal distributions (p < 0.05)**

📌 This justified the use of:

* Standardization
* Multivariate and unsupervised methods

---

### 3️⃣ Principal Component Analysis (PCA)

PCA was performed using scaled and centered gene-expression values.

#### Variance explained:

| Component | Variance (%) |
| --------- | ------------ |
| PC1       | 12.5%        |
| PC2       | 8.6%         |
| PC3       | 6.5%         |

Together, the first components capture the dominant biological variability.

---

### 4️⃣ PCA Interpretation

#### 🔹 Variable (Gene) Space

* Correlation circle used to visualize gene loadings
* Genes with longer vectors contribute more strongly
* Direction indicates correlation or opposition between genes

Notable contributors:

* **PC1:** POMC, ADCY3, PCSK1, LEPR
* **PC2:** NTRK2, CADM2, TMEM18

This reveals **distinct biological axes** related to appetite signaling and neuronal regulation.

---

### 5️⃣ Gene Clustering (k = 3)

Genes were clustered based on PCA coordinates:

* **Cluster 1:** Neuronal and synaptic regulation genes
* **Cluster 2:** Appetite and energy balance regulators
* **Cluster 3:** Hormonal and metabolic signaling genes

This grouping highlights functional modularity within obesity-related pathways.

---

### 6️⃣ Individual (Patient) Clustering (k = 3)

Clustering of individuals revealed:

* Two main dense groups near the PCA origin
* One clearly separated cluster with extreme PC1 values

This suggests the presence of **molecular sub-phenotypes** within the cohort.

---

### 7️⃣ Contribution Analysis

Barplots of variable contribution identified genes driving each axis:

* **PC1:** dominated by metabolic and hormonal genes
* **PC2:** enriched in neuronal development and signaling genes

Red dashed lines indicate the expected average contribution.

Genes above this threshold are biologically informative.

---

### 8️⃣ Heatmap of Gene Expression

* Scaled expression values
* Visual comparison across individuals
* Clear heterogeneity across samples

The heatmap supports PCA and clustering results, confirming structured variation rather than random noise.

---

### 9️⃣ BMI (IMC) Projection

Individuals were categorized as:

* Normal weight
* Overweight
* Obesity

When projected onto PCA space:

* Normal and overweight individuals largely overlap
* Obese individuals display greater dispersion

📌 This indicates:

> Obesity is associated with increased molecular heterogeneity rather than a single transcriptional profile.

---

## 📊 Main Conclusions

* Gene-expression profiles show **structured multivariate patterns**
* PCA successfully reduces dimensionality while preserving biological meaning
* Obesity-related genes cluster into functional modules
* Individuals with obesity show greater transcriptomic variability
* Molecular phenotypes cannot be explained by BMI alone

---

## 🧪 Tools & Libraries

* **R**
* tidyverse
* factoextra
* pheatmap
* gtsummary
* gt
* broom

---

## 📘 Files Included

* `actv3_g8.html` – full reproducible report
* `actv3_g8.docx` – formatted academic submission
* All figures generated directly from code

---

## ✍️ Authors

**Group 8 – Master in Bioinformatics**
January 2026

---

## 📜 License

This repository is intended for academic and educational use only.

---

✨ *This project demonstrates the application of unsupervised learning to biological systems, highlighting how multivariate statistics can reveal hidden structure in complex genomic data.*
