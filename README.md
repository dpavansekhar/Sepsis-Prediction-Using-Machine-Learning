# Sepsis-Prediction-Using-Machine-Learning

## 📌 Project Overview
This project focuses on **binary classification** of an **imbalanced dataset** using multiple machine learning models. Initially, models were trained on the imbalanced dataset, and later **Synthetic Minority Over-sampling Technique (SMOTE)** was applied to balance the dataset. The objective is to compare model performances before and after balancing the dataset using evaluation metrics such as **Accuracy, AUC-ROC, Precision, Recall, and F1-score**.

## 🛠️ Technologies Used
- **Python**
- **Scikit-Learn**
- **XGBoost**
- **Imbalanced-learn (SMOTE)**
- **Matplotlib & Seaborn (Visualization)**

## 🔍 Dataset Overview
The dataset contains binary labels (0 and 1), where one class is significantly underrepresented.
### **Preprocessing Steps:**
1. **Data Cleaning:** Handling missing values and irrelevant features.
2. **Feature Engineering:** Selecting important features for training.
3. **Data Splitting:** Dividing into **train (80%)** and **test (20%)**.

## 🏆 Models Implemented
We implemented and compared the following models:
1. **Logistic Regression**
2. **Random Forest**
3. **Gradient Boosting**
4. **XGBoost**
5. **Neural Networks**

## 🚀 Model Training & Evaluation
### **Step 1: Training on Imbalanced Dataset**
- All models were trained without any modifications to class distribution.
- Evaluation was performed using **Accuracy and AUC-ROC.**
- **Results:**
  - Models performed well in terms of **accuracy** (~90%) but had poor **AUC-ROC (~0.69)** due to class imbalance.

### **Step 2: Applying SMOTE for Balancing**
- **SMOTE (Synthetic Minority Over-sampling Technique)** was used to create a balanced dataset.
- Models were retrained on the balanced dataset.
- **Results:**
  - **Accuracy dropped (~50-56%)**, but **AUC-ROC remained similar (~0.68-0.69).**
  - Indicates that oversampling improved the class balance but made classification harder.

### **Step 3: Model Fine-Tuning**
To improve performance, **Gradient Boosting** and **XGBoost** were fine-tuned using **RandomizedSearchCV**:
- **Hyperparameters Tuned:** Learning Rate, Number of Estimators, Maximum Depth, etc.
- **Results:**
  - Improved **AUC-ROC** and better stability in accuracy.

## 📊 Results & Comparison
| Model | Accuracy (Imbalanced) | AUC-ROC (Imbalanced) | Accuracy (Balanced) | AUC-ROC (Balanced) |
|------------|--------------------|--------------------|------------------|------------------|
| Logistic Regression | 0.9093 | 0.6940 | 0.5621 | 0.6832 |
| Random Forest | 0.9092 | 0.6915 | 0.5524 | 0.6803 |
| Gradient Boosting | 0.9093 | 0.6944 | 0.5265 | 0.6856 |
| XGBoost | 0.9093 | 0.6928 | 0.5401 | 0.6852 |
| Neural Network | 0.9096 | 0.6840 | 0.5222 | 0.6844 |

## 📈 Conclusion
- **Best Model for Balanced Data:** **Gradient Boosting & XGBoost (after fine-tuning)** as they showed **higher AUC-ROC and stability**.
- **Accuracy Dropped After Balancing:** Since the dataset had oversampled minority instances, models faced challenges in distinguishing classes, leading to lower accuracy.
- **AUC-ROC Remained Consistent:** Showing that class separation did not degrade significantly.
- **Fine-tuning Improved Results:** Optimizing hyperparameters helped models regain some lost performance.

## 🔥 Future Work
- Try **cost-sensitive learning** to handle imbalanced data without oversampling.
- Implement **Ensemble methods** for better generalization.
- Explore **deep learning architectures** for better feature learning.

## 📝 Author
Developed by **[Your Name]**, a **Machine Learning Enthusiast** aiming to optimize imbalanced classification problems.

