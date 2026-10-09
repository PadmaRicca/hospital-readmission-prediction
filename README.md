# Hospital Readmission Prediction Using Machine Learning

**Project Level:** Postgraduate

**Author:** Padma Michela Ricca  
**Institution:** University College London (UCL)  
**Degree:** MSc Artificial Intelligence for Biomedicine and Healthcare  
**Module:** COMP0189 (Applied Artificial Intelligence)  
**Assessment Outcome:** 87% (Distinction)  
**Overall Module Mark:** 79.17% (Distinction)  
**Project Type:** Applied machine learning, clinical data processing, predictive modelling and experimental evaluation project

## Project Overview

Developed and evaluated supervised machine learning models to predict hospital readmission among patients with diabetes, using a publicly available clinical dataset comprising 101,766 hospital encounters and 50 recorded variables.

The project involved an extensive, implementation-focused workflow, progressing from exploratory data analysis and clinically informed feature engineering to model development, hyperparameter optimisation, nested cross-validation and interpretability analysis. Particular emphasis was placed on addressing real-world data challenges, preventing data leakage and critically evaluating methodological choices through controlled experiments.

Gradient Boosting achieved the strongest performance, with a mean balanced accuracy of 61.10%, F1-score of 0.6062 and ROC AUC of 0.6531 across held-out outer cross-validation folds. Although it consistently outperformed the linear alternatives, its modest predictive performance highlighted the difficulty of predicting hospital readmissions using routinely collected clinical records. The results were obtained on a balanced modelling subset and do not establish clinical validity.

## Contributions

- Conducted comprehensive exploratory data analysis, examining class distributions, feature-target relationships, missingness, skewness, outliers and multicollinearity, identifying ten key dataset challenges and their implications for predictive modelling.
- Constructed a patient-level modelling dataset by binarising readmission outcomes, excluding expired or hospice patients and invalid records, retaining the first encounter per patient to prevent patient overlap across folds, and applying controlled under-sampling to obtain 20,000 balanced observations.
- Developed a preprocessing workflow addressing severely incomplete and near-constant features, hidden missing-value codes and ordinal age representation, while preserving unknown ethnicity rather than introducing potentially unreliable imputations. Integrated numerical standardisation and categorical encoding into scikit-learn pipelines to prevent training-fold statistics from leaking into validation data.
- Implemented a custom ICD-9-CM diagnosis grouping strategy, reducing over 700 distinct codes in each diagnosis field into approximately 20 clinically meaningful categories, with Diabetes retained separately to preserve relevant medical information and limit dimensionality.
- Designed and trained Linear Support Vector Machines, L1-regularised Logistic Regression and Gradient Boosting models, using nested five-fold stratified cross-validation for hyperparameter tuning and generalisation assessment. Optimised balanced accuracy while tracking F1-score, ROC AUC, precision and recall to capture complementary aspects of classification performance.
- Investigated hyperparameter sensitivity across the three architectures, identifying the benefits of stronger regularisation for Linear SVMs, excessive coefficient shrinkage in heavily penalised Logistic Regression and potential overfitting in more complex Gradient Boosting configurations.
- Evaluated prediction stability and class-specific errors through performance distributions, ROC curves and confusion matrices, observing that Gradient Boosting achieved modest but consistent improvements across all five metrics, with higher readmission recall at the expense of additional false positives.
- Combined model-specific coefficients and feature importances with held-out permutation importance analysis, identifying prior inpatient visits, diagnosis count, previous emergency visits and admission type as influential predictors. Examined how nonlinear models capture broader feature relationships while linear coefficients can be sensitive to rare encoded categories.
- Conducted an additional feature-selection experiment incorporating SelectKBest (ANOVA F-test) into the Gradient Boosting pipeline, jointly optimising the feature subset size and classifier hyperparameters. Observed a reduction in balanced accuracy from 61.10% to 60.62%, suggesting that univariate filtering can discard information valuable for nonlinear feature interactions, despite reducing dimensionality.

## Skills Demonstrated

- **Applied Machine Learning:** Practical understanding of supervised classification, algorithm selection, regularisation strategies, hyperparameter optimisation and generalisation assessment.
- **Clinical Data Processing and Feature Engineering:** Preparing heterogeneous healthcare records, incorporating medical domain knowledge and addressing missing information, categorical complexity and patient-level data integrity.
- **Model Interpretation and Explainable AI:** Investigating predictor relevance, interpreting differences between linear and nonlinear architectures and recognising the limitations of feature importance measures.
- **Experimental Design and Statistical Analysis:** Constructing systematic comparisons, analysing performance variability, evaluating bias-variance and feature-selection trade-offs, and drawing evidence-based conclusions from both positive and negative findings.
- **Scientific Programming and Technical Documentation:** Implementing structured computational workflows using Python, pandas, NumPy, scikit-learn, Matplotlib and Seaborn, with reproducible random seeds, experimental visualisations and clear communication of technical findings.

## Report Availability

The original assessed Jupyter notebook, academic report and results are currently withheld from public access to uphold academic integrity.

This repository provides an overview of the project's objectives, applied machine learning approach, experimental methodology, evaluation findings and skills demonstrated.

Technical documentation and implementation materials may be made available upon request, in accordance with the University's policies.
