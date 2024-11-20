# Microsoft: Classifying Cybersecurity Incidents with Machine Learning

## Project Overview

In this project, we tackle a critical problem in cybersecurity: automating the triage process for Security Operation Centers (SOCs). By leveraging the comprehensive GUIDE dataset, we aim to develop a machine learning model that classifies incidents as:

- **True Positive (TP)**  
- **Benign Positive (BP)**  
- **False Positive (FP)**  

The primary goal is to enhance SOC efficiency by providing analysts with precise, context-rich recommendations. This project supports the development of guided response systems to improve the overall security posture of enterprise environments.

---

## Skills and Knowledge Gained

- **Data Preprocessing**: Handling missing data, feature engineering, and encoding techniques.  
- **Machine Learning Techniques**: Training and evaluating classification models, including hyperparameter tuning.  
- **Evaluation Metrics**: Emphasis on macro-F1 score, precision, and recall for model evaluation.  
- **Cybersecurity Frameworks**: Incorporating MITRE ATT&CK techniques and understanding the domain.  
- **Handling Imbalanced Data**: Techniques like SMOTE and ensemble methods for robust performance.  

---

## Business Use Cases

### 1. Security Operation Centers (SOCs)  
Automate the triage process to prioritize critical threats efficiently.

### 2. Incident Response Automation  
Enable systems to suggest appropriate actions for incident mitigation.

### 3. Threat Intelligence  
Enhance detection capabilities using historical evidence and customer responses.

### 4. Enterprise Security Management  
Reduce false positives and ensure timely addressing of true threats.

---

## Dataset Overview

The **GUIDE** dataset features over 1 million annotated incidents with triage labels and detailed telemetry from 6,100+ organizations, spanning 441 MITRE ATT&CK techniques. Key components:

- **Training Data**: 70% of incidents  
- **Testing Data**: 30% of incidents  
- **Primary Metric**: Macro-F1 score for classification.  

**Privacy Note**: All sensitive data underwent anonymization (SHA1 hashing, random ID replacement, temporal noise).

---

## Project Workflow

### 1. **Data Preprocessing and EDA**
- Removed columns with >50% missing values.
- Engineered features like `Hour`, `Day`, and `Time` from timestamps.
- Encoded categorical features using `LabelEncoder`.

### 2. **Exploratory Data Analysis (EDA)**
- Visualized incident distributions across time and categories.
- Identified class imbalances in the target variable.

### 3. **Model Training and Evaluation**
- Baseline models: Logistic Regression and Decision Tree.
- Advanced models: Random Forest, Gradient Boosting, XGBoost, and LightGBM.
- Addressed class imbalance using **SMOTE**.
- Selected **XGBoost** with the top 11 features for optimal performance.

### 4. **Hyperparameter Tuning**
- Optimized `XGBoost` hyperparameters with RandomizedSearchCV to enhance F1-scores.

### 5. **Feature Importance**
- Used SHAP for feature importance analysis.
- Top features: `OrgId`, `IncidentId`, `AlertTitle`, `DetectorId`, etc.

### 6. **Final Evaluation**
- Validated on a separate test set to ensure model generalization.
- Achieved high macro-F1 score and balanced class-wise performance.

---

## Results

- **Top Performing Model**: XGBoost with hyperparameter tuning and SMOTE.
- **Key Metrics**:  
  - Macro-F1 Score: *High*  
  - Precision and Recall: Consistent across TP, BP, FP classes.  
- **Top Features**: Insights from SHAP analysis enabled computational efficiency and improved results.

---

## Recommendations for Deployment

1. **Integration into SOC Workflows**:
   - Real-time classification and guided response.
2. **Scalability**:
   - Leverage cloud services for high-volume data handling.
3. **Feedback Loop**:
   - Continuous model improvement using SOC analyst feedback.

---

## Technical Details

**Tools and Libraries**:  
- Python, Jupyter Notebook  
- Libraries: scikit-learn, XGBoost, LightGBM, SHAP, Pandas, Seaborn  

**Cloud Services**:  
- Google Cloud (BigQuery, Compute Engine, Cloud Storage)

**Version Control**: GitHub  

---

## Contact and Acknowledgments

**Dataset Source**: Microsoft Security AI Research  
**For inquiries**:  
- Scott Freitas: scottfreitas@microsoft.com  
- Jovan Kalajdjieski: jovank@microsoft.com  
