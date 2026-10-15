#  README.md Content

# SMS Spam Classification with Multiple Classifiers

This repository contains a Jupyter Notebook implementing an SMS Spam Classifier comparing multiple machine learning models including Support Vector Machines (SVM), Random Forest, LightGBM, and K-Nearest Neighbors (KNN).

## Table of Contents
- [Dataset](#dataset)
- [Project Overview](#project-overview)
- [Models Evaluated](#models-evaluated)
- [Comparison Results](#comparison-results)
- [Dependencies](#dependencies)

## Dataset

- **Source**: [Kaggle - SMS Spam Collection Dataset](https://www.kaggle.com/datasets/uciml/sms-spam-collection-dataset)
- Features: `message` (text payload), `char_count`, `word_count`, and `label` (0 for Ham, 1 for Spam).

## Project Overview

This project evaluates and compares different classification algorithms to determine the most effective approach for detecting spam messages using a TF-IDF representation.

## Models Evaluated

1. **Linear Support Vector Machine (LinearSVC)**
2. **Random Forest Classifier**
3. **LightGBM Classifier**
4. **K-Nearest Neighbors (KNN)**

## Comparison Results

Below is the performance comparison of the classifiers on the test dataset:

| Model | Accuracy | Precision | Recall | F1-Score |
| :--- | :---: | :---: | :---: | :---: |
| **Linear SVM** | **98.45%** | 98.32% | **89.31%** | **93.60%** |
| **Random Forest** | 97.49% | 98.17% | 81.68% | 89.17% |
| **LightGBM** | 97.39% | 94.83% | 83.97% | 89.07% |
| **KNN** | 90.52% | **100.00%** | 25.19% | 40.24% |

### Key Findings:
- **Linear SVM** achieved the highest overall performance with an F1-Score of **93.60%**.
- **KNN** achieved perfect precision (**100.00%**) but suffered from very low recall (**25.19%**), missing many spam messages.
- **Random Forest** and **LightGBM** offered strong alternative baselines near ~**89%** F1-score.

## Dependencies

```bash
pip install pandas numpy matplotlib seaborn wordcloud nltk scikit-learn lightgbm
```
