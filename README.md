# Fairness in Credit Scoring: German Credit Data

This project explores algorithmic bias in credit scoring models and applies fairness-aware machine learning techniques to mitigate gender-based discrimination. Using the German Credit dataset and the AIF360 fairness toolkit by IBM, we demonstrate how various preprocessing, in-processing, and post-processing methods affect both model performance and fairness metrics. Scripts can be found in the PDF with report.

## 📌 Project Goals

- Develop a binary classifier for creditworthiness prediction using CatBoost
- Identify and mitigate gender bias (male vs female) in model outputs
- Compare fairness/performance trade-offs across mitigation techniques
- Provide business justification for applying fairness-aware models in finance

## 🧠 Methods

### 1. Dataset
- **German Credit Dataset** from UCI Machine Learning Repository
- 20 original features (after encoding expanded to 58)
- Protected attribute: `sex` (binary: male/female)

### 2. Bias Mitigation Techniques (via AIF360)
- **Pre-processing:** `Reweighing`
- **In-processing:** `GridSearchReduction`, `AdversarialDebiasing`
- **Post-processing:** `Equalized Odds Postprocessing`

### 3. Fairness Metrics
- **Demographic Parity**
- **Equal Opportunity Difference**
- **Average Odds Difference**

### 4. Performance Metrics
- **Accuracy**
- **False Positive Rate (FPR)**
- **Balanced Accuracy**

## 📊 Results Summary

| Technique                | Accuracy | FPR  | Demographic Parity | Equal Opportunity |
|--------------------------|----------|------|---------------------|--------------------|
| Baseline (Perf. only)    | 0.77     | 0.17 | 1.28                | N/A                |
| Reweighing (Preprocess)  | 0.77     | 0.17 | 1.03                | -0.01              |
| GridSearch (Inprocess)   | 0.76     | 0.18 | 1.02                | -0.10              |
| Adversarial Debiasing    | 0.64     | 0.22 | 1.07                | 0.03               |
| Equalized Odds (Post)    | 0.64     | 0.45 | 1.07                | 0.03               |

🔎 **Conclusion:** Reweighing offers the best trade-off between fairness and performance.

## 🏢 Business Impact

- Supports **regulatory compliance** with anti-discrimination laws (e.g., GDPR, ECOA)
- Enhances trust and transparency in automated decision-making
- Provides a foundation for fair credit models in financial services

## 🧑‍🤝‍🧑 Authors

- Anirban Das  
- Jan Frąckowiak  
- Antoni Piotrowski

## 📄 License

This project is for academic purposes only and does not constitute legal or business advice.

