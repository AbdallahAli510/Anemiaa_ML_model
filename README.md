# Anemia Classification with CBC Data

This repository demonstrates end-to-end development of a machine-learning pipeline for anemia detection and subtype classification from Complete Blood Count (CBC) measurements.

---

## 📄 Project Description

Anemia affects millions worldwide; timely screening using routine CBC tests can help detect and classify anemia subtypes (e.g., iron-deficiency, hemolytic) or normal hematological profiles. This notebook shows how to:

1. **Load & Explore**: Import CBC data, examine distributions, handle missing values/outliers.  
2. **Feature Engineering**: Compute derived ratios (e.g., Neutrophils-to-Lymphocytes), encode categorical variables.  
3. **Modeling**: Train and compare multiple classifiers (Random Forest, XGBoost, SVM) with cross-validation.  
4. **Evaluation**: Visualize performance via confusion matrices, ROC curves, and classification reports.  
5. **Serialization**: Save the best model for later inference and deployable use.

---


---

## 🧩 Code Walkthrough

1. **Data Loading & Inspection**  
   - Read CSV into pandas DataFrame  
   - Display `.head()`, `.info()`, and `.describe()`  
   - Check class balance (`df['Condition'].value_counts()`)

2. **Data Cleaning & Preprocessing**  
   - Impute or drop missing values  
   - Encode categorical features (`OneHotEncoder` or `LabelEncoder`)  

3. **Feature Engineering**  
   - Create new ratios (e.g., `neutrophil_pct / lymphocyte_pct`)  
   - Scale numeric features (`StandardScaler` or `MinMaxScaler`)  

4. **Train/Test Split**  
   - Stratified split to preserve label distribution  
   - Use `train_test_split(random_state=42, stratify=y)`

5. **Model Selection & Cross-Validation**  
   - Instantiate pipelines combining scaler + classifier  
   - Compare `RandomForestClassifier`,  `SVC` 
   - Optimize hyperparameters (e.g., number of trees, max depth)

6. **Evaluation & Visualization**  
   - Compute accuracy, precision, recall, F1-score  
   - Plot confusion matrix and per-class ROC curves  
   - Log results in a summary table

7. **Model Saving & Loading**  
   - Save best estimator with `joblib.dump()`  
   - Provide example of `joblib.load()` and inference on new samples

---

## ⚙️ Installation & Setup

1. **Clone the repository**  
   ```bash
   git clone https://github.com/your-username/anemia-classification.git
   cd anemia-classification
