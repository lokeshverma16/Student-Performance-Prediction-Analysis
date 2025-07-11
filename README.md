# 🎓 Student Performance Prediction Analysis

*Predicting academic outcomes using machine learning to enable data-driven educational interventions*

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://python.org)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0+-orange.svg)](https://scikit-learn.org)
[![Pandas](https://img.shields.io/badge/Pandas-1.3+-green.svg)](https://pandas.pydata.org)

## 📋 Executive Summary

This project implements a comprehensive machine learning pipeline to predict student final grades using demographic, social, and academic features. Through rigorous data analysis and modeling, the system achieved **82.1% accuracy (R² = 0.821)** in predicting student outcomes, identifying key factors that influence academic success and providing actionable insights for educational interventions.

The analysis processes 1,044 student records across Mathematics and Portuguese language courses, demonstrating the power of data science in educational settings. The final model serves as an early warning system, flagging 32% of at-risk students with 95.3% recall and 61.2% precision.

## 🎯 Project Overview

### Objectives
- Predict student final grades (G3) with high accuracy across two academic subjects
- Identify critical factors influencing student academic performance  
- Develop an early warning system for proactive educational intervention
- Create actionable insights for resource allocation and support strategies

### Key Results
- **Best Model**: Gradient Boosting Regressor with R² = 0.821, RMSE = 1.592
- **Feature Insights**: Prior academic performance (G1, G2) and study habits are strongest predictors
- **Business Impact**: Early warning system identifies 95.3% of at-risk students for targeted intervention

## 📊 Dataset Description

**Source**: UCI Student Performance Dataset  
**Size**: 1,044 student records (395 Math, 649 Portuguese)  
**Features**: 33 original features across multiple categories:

- **Academic Features**: Previous grades (G1, G2), study time, past failures
- **Demographic Features**: Age, gender, urban/rural address, family size
- **Socio-Economic Features**: Parent education levels, family jobs, support systems
- **Behavioral Features**: Social activities, alcohol consumption, relationships

**Target Variable**: Final grade (G3) on a 0-20 scale

## 🔄 Project Pipeline

### 1. Data Loading & Quality Assessment
- Combined Mathematics and Portuguese datasets
- Verified data integrity (no missing values, no duplicates)
- Initial statistical profiling and distribution analysis

### 2. Exploratory Data Analysis (EDA)
- **Grade Distribution Analysis**: Portuguese students show slightly higher performance
- **Correlation Analysis**: Strong correlation between prior grades (G1, G2) and final outcomes
- **Feature Relationships**: Identified key patterns in study habits, failures, and social factors
- **Interactive Visualizations**: Comprehensive dashboard showing performance drivers

### 3. Feature Engineering & Preprocessing
- **New Features Created**:
  - `total_alcohol`: Combined weekday and weekend alcohol consumption
  - `at_risk`: Binary indicator based on multiple risk factors
- **Preprocessing Pipeline**:
  - StandardScaler for numerical features
  - OneHotEncoder for categorical variables
  - Proper handling of nominal vs. binary features
- **Train-Test Split**: 80-20 split with stratification on risk factors

### 4. Model Development & Training
**Models Evaluated**:
- Linear Regression (baseline)
- Random Forest Regressor
- Gradient Boosting Regressor

**Model Selection**: Gradient Boosting chosen based on cross-validation performance

### 5. Model Evaluation & Validation
- **Performance Metrics**: R², RMSE, MAE
- **Cross-Validation**: 5-fold CV to ensure model stability
- **Residual Analysis**: Diagnostic plots to assess model assumptions

### 6. Model Interpretation & Feature Importance
- Feature importance analysis for business insights
- Prediction vs. actual performance visualization
- Residual analysis for model diagnostics

### 7. Business Impact Analysis
- Early warning system evaluation (precision, recall, specificity)
- Resource allocation optimization insights
- Actionable recommendations for educational stakeholders

## 🏆 Model Performance

| Model | R² Score | RMSE | MAE | CV R² Mean | CV R² Std |
|-------|----------|------|-----|------------|-----------|
| **Gradient Boosting** | **0.821** | **1.592** | **1.188** | **0.870** | **0.023** |
| Linear Regression | 0.819 | 1.601 | 1.196 | 0.833 | 0.027 |
| Random Forest | 0.808 | 1.651 | 1.238 | 0.860 | 0.025 |

### Early Warning System Performance
- **Precision**: 61.2% (of flagged students who are actually at-risk)
- **Recall**: 95.3% (of at-risk students successfully identified)
- **Specificity**: 84.3% (of not-at-risk students correctly ignored)

## 🔍 Key Insights

### Critical Success Factors
1. **Prior Academic Performance**: Previous grades (G1, G2) are the strongest predictors
2. **Study Habits**: Weekly study time shows significant positive correlation
3. **Academic History**: Past failures have strong negative impact on outcomes
4. **Family Support**: Parental education and family support systems matter
5. **Social Factors**: Excessive social activities correlate with lower performance

### Actionable Recommendations
- **Early Intervention**: Deploy model predictions after first grading period
- **Targeted Support**: Focus resources on students with past failures
- **Study Skills Training**: Implement workshops for effective study techniques
- **Parental Engagement**: Enhance communication with families of at-risk students

## 🚀 Getting Started

### Prerequisites
```bash
Python 3.8+
```

### Dependencies
```bash
pip install pandas numpy scikit-learn matplotlib seaborn jupyter
```

### Installation & Setup
1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd student-outcome-prediction
   ```

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

3. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook student_performance_analysis-run.ipynb
   ```

4. **Run the analysis**
   - Execute all cells sequentially
   - Total runtime: ~5-10 minutes
   - View results in generated visualizations and summary tables

### Required Files
- `student-mat.csv` - Mathematics course data
- `student-por.csv` - Portuguese course data

## 📁 Project Structure
```
student-outcome-prediction/
├── README.md
├── student_performance_analysis-run.ipynb    # Main analysis notebook
├── student-mat.csv                          # Mathematics dataset
├── student-por.csv                          # Portuguese dataset
└── requirements.txt                         # Python dependencies
```

## 🛠️ Technologies Used

**Core Libraries**:
- **Pandas & NumPy**: Data manipulation and numerical computing
- **Scikit-learn**: Machine learning algorithms and preprocessing
- **Matplotlib & Seaborn**: Data visualization and statistical plotting

**Advanced Techniques**:
- **ColumnTransformer**: Robust preprocessing pipeline
- **Cross-Validation**: Model stability assessment  
- **Feature Engineering**: Domain-specific feature creation
- **Model Interpretation**: Feature importance and residual analysis

## 📈 Future Enhancements

### Technical Improvements
- **Deep Learning Models**: Neural networks for complex pattern recognition
- **Ensemble Methods**: Advanced stacking and voting classifiers
- **Real-time API**: Flask/FastAPI deployment for live predictions
- **Feature Selection**: Advanced techniques like SHAP for interpretability

### Data Expansion
- **Multi-school Validation**: Cross-institutional model testing
- **Longitudinal Analysis**: Multi-year student tracking
- **Additional Features**: Socioeconomic indicators, mental health factors
- **Real-time Integration**: LMS and attendance system data

## 📝 License

This project uses the UCI Student Performance Dataset, available for research and educational purposes.

**Dataset Citation**: P. Cortez and A. Silva. Using Data Mining to Predict Secondary School Student Performance. Proceedings of 5th Future Business Technology Conference (FUBUTEC 2008), Porto, Portugal, April 2008.

---

*Developed by Lokesh Verma | Demonstrating practical applications of machine learning in educational analytics* 