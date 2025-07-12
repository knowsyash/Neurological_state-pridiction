# Neurological State Prediction: Conference Research Project
# Conference Paper Summary
This project is based on our accepted conference research paper, presenting a novel approach to neurological state prediction using physiological time-series data. As research interns at MANIT Bhopal, we developed and validated a pipeline that combines supervised and semi-supervised machine learning models to classify neurological states from sensor data. Our methodology includes advanced feature engineering, windowing, clustering, and classification, with extensive evaluation of model accuracy and robustness.

**Key highlights from the paper:**
- Demonstrates the effectiveness of combining supervised and semi-supervised learning for physiological data.
- Shows that windowed feature extraction and majority voting improve label quality and model performance.
- Provides a comparative analysis of algorithms (Logistic Regression, Random Forest, XGBoost, Label Spreading) and their strengths in different data scenarios.
- Offers practical insights for real-world deployment in clinical and research settings.

For a comprehensive explanation of our methodology, results, and scientific impact, please refer to the full research paper PDF.

**[Download the Conference Paper PDF](#)**  <!-- Replace # with your actual PDF link when available -->
# Research Context & Importance
This project was conducted as part of a research internship at MANIT Bhopal by Yash Singhal, Yash Singh, and Suddepti Singh. As research interns, we undertook this work to contribute to the advancement of neurological state prediction using machine learning. The project is highly significant due to its real-world impact, academic value, and its role in supporting our conference research paper. Our work at MANIT Bhopal provided us with the resources and mentorship to explore innovative approaches in supervised and semi-supervised learning for physiological data analysis.

## Overview
This project presents a comprehensive approach to predicting neurological states using physiological time-series data. Developed for a conference research paper by Yash Singhal, Yash Singh, and Suddepti Singh, the repository includes all code, data, and analysis required to reproduce our results. The associated research paper PDF will be linked here once provided.

## Project Motivation
Neurological state prediction is crucial for early detection and monitoring of pain, stress, and other cognitive states. Our work leverages supervised learning and unsupervised clustering on physiological signals (EDA, HR, SpO2, Temp, Accelerometer) collected from multiple subjects, aiming to advance automated state assessment in clinical and research settings.

## Authors
- Yash Singhal
- Yash Singh
- Suddepti Singh

## Conference Paper
**This repository supports our accepted conference research paper.**
- [Download PDF](#)  <!-- Replace # with your actual PDF link when available -->

## Project Objective
Our main objective is to compare the results and accuracy of supervised learning and semi-supervised learning models for neurological state prediction. We use multiple algorithms (XGBoost, Random Forest, Logistic Regression, Label Spreading) and analyze their performance on physiological datasets. The project observes how different models perform, highlights strengths and weaknesses, and discusses accuracy and findings for each approach.

## Why Perform EDA?
Exploratory Data Analysis (EDA) is essential to:
- Understand data distributions, missing values, and outliers
- Visualize relationships and correlations between features
- Guide feature engineering and model selection
- Ensure data quality and reliability for downstream modeling

The EDA report (`EDA/ydata.html`) provides:
- Overview of dataset structure and variables
- Distribution and frequency of key features (SpO2, HR, AccX, AccY, AccZ, Temp, EDA, Age, Gender, Subject)
- Correlation analysis, missing value summary, and duplicate row detection

## Libraries Used & Their Purpose
**Data Handling & Visualization:**
- pandas, numpy: Data manipulation and analysis
- matplotlib, seaborn, plotly: Data visualization
- ydata-profiling: Automated EDA report generation

**Preprocessing & Feature Engineering:**
- sklearn.preprocessing (StandardScaler, LabelEncoder): Feature scaling and encoding
- scipy.stats: Statistical analysis (mode, skew, kurtosis, entropy)

**Modeling:**
- sklearn.linear_model (LogisticRegression): Supervised classification
- sklearn.ensemble (RandomForestClassifier): Supervised classification
- xgboost (XGBClassifier): Advanced supervised classification
- sklearn.semi_supervised (LabelSpreading): Semi-supervised learning
- sklearn.decomposition (PCA): Dimensionality reduction

**Evaluation & Tuning:**
- sklearn.metrics (classification_report, accuracy_score): Model evaluation
- sklearn.model_selection (train_test_split, GridSearchCV, RandomizedSearchCV, cross_val_score): Model selection and hyperparameter tuning
- optuna: Automated hyperparameter optimization

**Other:**
- IPython.display: Enhanced notebook outputs
- pathlib: File path handling

## Repository Structure
- `Project.ipynb`: Main notebook for unsupervised learning, feature engineering, clustering, and dimensionality reduction.
- `Supervised_learning.ipynb`: Supervised classification pipeline, data cleaning, feature scaling, model training, and evaluation.
- `DATA/`: Contains all datasets used, including raw and processed CSV files.
- `EDA/`: Exploratory Data Analysis reports.
- `temp_backup/`: Backup copies of key datasets.

## Data Description
- **pain_dataset_all_subjects.csv**: Raw physiological data from multiple subjects.
- **Supervised_dataset.csv**: Cleaned and labeled dataset for supervised learning.
- **windowed_features.csv / timeseries_windowed_features.csv**: Extracted features from time-series windows.

## Methodology
### 1. Data Preprocessing
- Missing value analysis and imputation
- Outlier detection and handling (IQR, Z-score, medical/sensor validity clipping)
- Feature scaling (StandardScaler)
- Windowing of time-series data for feature extraction

### 2. Feature Engineering
- Statistical features: mean, std, min, max, range, slope, skew, kurtosis
- Signal features: peak count, entropy, FFT-based features
- Dimensionality reduction (PCA)

### 3. Unsupervised Learning
- KMeans clustering on windowed features
- DBSCAN and hierarchical clustering for cluster validation
- Cluster quality metrics: Silhouette Score, Davies-Bouldin Index, intra/inter-cluster distances

### 4. Supervised Learning
- XGBoost, Random Forest, Logistic Regression classifiers for neurological state prediction
- Hyperparameter tuning (GridSearchCV, RandomizedSearchCV, Optuna)
- Model evaluation: accuracy, recall, classification report

### 5. Semi-Supervised Learning
- Label Spreading algorithm to leverage both labeled and unlabeled data
- Compare performance with supervised models
- Observe accuracy, robustness, and generalization

## Setup Instructions
1. **Clone the repository**
   ```powershell
   git clone https://github.com/knowsyash/Neurological_state-pridiction.git
   cd Neurological_state-pridiction
   ```
2. **Install Python dependencies**
   - Recommended: Python 3.8+
   - Install required packages:
     ```powershell
     pip install numpy pandas matplotlib seaborn scikit-learn xgboost plotly jinja2 antropy
     ```
3. **Run the notebooks**
   - Open `Project.ipynb` and `Supervised_learning.ipynb` in Jupyter or VS Code.
   - Follow the notebook cells for step-by-step analysis and model training.

## Results & Findings
**Key features:** EDA, HR, Temp, SpO2, Acc_magnitude
**Clustering:** 4 clusters identified, validated by multiple metrics
**Classification:**
- XGBoost, Random Forest, Logistic Regression: High accuracy and recall for state prediction
- Label Spreading (semi-supervised): Utilizes both labeled and unlabeled data, compared for accuracy and robustness
**Outlier handling:** Robust cleaning improves model reliability
**Comparison:** Results and accuracy of supervised vs. semi-supervised models are observed and discussed in detail in the notebooks. Insights are provided on which models perform best and under what conditions.

## Insights & Conclusions from Notebooks

### P1.ipynb
- Performs unsupervised clustering (KMeans, PCA) on physiological features.
- Evaluates cluster quality using Silhouette Score and Davies-Bouldin Index (e.g., Silhouette ~0.36, DB ~1.03 for best clustering).
- Visualizes clusters and dimensionality reduction results.
- Practical insight: Clustering reveals structure in physiological data, and cluster metrics help select optimal parameters.
- Conclusion: Unsupervised clustering provides a strong foundation for feature engineering and downstream supervised learning.

### Project.ipynb
- Explores unsupervised learning and clustering on physiological features.
- Performs feature engineering, windowing, and dimensionality reduction (PCA).
- Uses KMeans, DBSCAN, and hierarchical clustering to identify natural groupings in the data.
- Evaluates cluster quality and visualizes results.
- Conclusion: Physiological signals can be grouped into meaningful clusters, supporting further supervised analysis.

### Supervised_learning.ipynb
- Focuses on supervised classification using labeled data.
- Cleans and preprocesses the dataset, handles outliers, and scales features.
- Trains and tunes XGBoost and other classifiers to predict neurological states.
- Compares model performance and provides detailed accuracy and recall metrics.
- Conclusion: Supervised models achieve strong predictive performance, with XGBoost and Random Forest showing high accuracy.

### P2.ipynb

### P2.ipynb
- Integrates supervised and semi-supervised learning (Label Spreading, Logistic Regression, Random Forest, XGBoost).
- Uses StandardScaler and PCA for feature scaling and dimensionality reduction.
- Predicts labels for both labeled and unlabeled data, saving results to CSV for further analysis.
- Visualizes predicted label distributions and evaluates accuracy (e.g., semi-supervised accuracy ~0.68).
- Compares precision, recall, and F1-score for each model, highlighting strengths and weaknesses.
- Practical insight: Semi-supervised learning boosts performance when labeled data is scarce, while supervised models excel with more labels.
- Conclusion: Combining supervised and semi-supervised approaches provides robust predictions and deeper insights into physiological state classification.

### Use of Supervised Windowed CSV Files
- The supervised windowed CSV files (e.g., `Supervised_windowed.csv`) are used in the notebooks to provide labeled, windowed features for model training and evaluation.
- These files are loaded, cleaned, and processed to extract statistical and signal features for each time window.
- They enable both supervised and semi-supervised models to learn from segmented physiological data, improving prediction accuracy and robustness.

## How to Cite
If you use this code or data, please cite our conference paper (link above).

## Contact
For questions or collaboration, contact:
- yashsinghal@example.com
- yashsingh@example.com
- suddeptisingh@example.com

---
*Made by Yash Singhal, Yash Singh, and Suddepti Singh for conference research.*
