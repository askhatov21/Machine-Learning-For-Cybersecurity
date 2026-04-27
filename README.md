# Machine-Learning-For-Cybersecurity

# Students: Swan Htet Zaw, The Bao Le, Amir Askhatov (Group 3)
 Course: CP2421 – Machine Learning for Cybersecurity

📋 Project Overview
This group research project compares two machine learning algorithms — Random Forest and K-Nearest Neighbours (KNN) — for detecting botnet traffic using a real-world network dataset. The goal is to evaluate which model performs better at identifying malicious botnet flows versus benign traffic, and assess their suitability for real-time deployment.

📁 Files

Assement3_Report.pdf              # Full group research report
 
practicals 2-10                      # Weekly practical notebooks (coming soon)

README.md

🗂️ Dataset
DetailInfoNameCTU-13 (capture20110810.binetflow)Size427,302 samples × 24 numeric featuresSplit70% training / 30% testingLabelBinary — 1 = Botnet, 0 = BenignClass imbalanceBenign heavily dominates (127,574 vs 617 botnet in test set)
Preprocessing steps:

Skipped first 8 metadata rows on load
Dropped non-numeric columns (IP addresses, protocol names)
Removed rows with missing values
Binary label created: flows containing 'Botnet' → 1, else → 0


🧠 Models
Model 1 – Random Forest Classifier

100 decision trees (n_estimators=100, random_state=42)
Ensemble method; robust to noise and class imbalance
Fast inference (traverses fixed tree depth)

Model 2 – K-Nearest Neighbours (KNN)

k=3, Euclidean distance (Minkowski metric, p=2)
Lazy learner; computes distances at prediction time
Sensitive to feature scale; relies on quality preprocessing


📊 Results
MetricRandom ForestKNNOverall Accuracy1.001.00Botnet Precision1.000.94Botnet Recall0.960.89Botnet F1-Score0.980.91False Positives132False Negatives2470

✅ Winner: Random Forest — significantly fewer false positives and false negatives on the minority botnet class, which matters most in a real security context.


🔬 Key Findings

Both models achieved near-perfect overall accuracy, but this is misleading due to class imbalance (the majority benign class dominates the score).
Random Forest was clearly superior at detecting the minority botnet class — fewer missed attacks (FN: 24 vs 70) and fewer false alarms (FP: 1 vs 32).
KNN struggled without additional feature engineering or tuning; its distance-based approach is sensitive to imbalanced data.
For real-time deployment, RF is more practical — inference is fast and parallelisable, while KNN scales poorly with dataset size.


🛠️ Tools & Libraries
ToolPurposePythonPrimary programming languageGoogle ColabDevelopment environmentpandas / numpyData loading and preprocessingscikit-learnModel training, evaluation, confusion matrixmatplotlib / seabornPerformance visualisation
🔗 Google Colab Notebook

📓 Practicals (Weeks 1–10)

🚧 Coming Soon

Weekly practical notebooks will be added here as they are completed. Each will cover a different ML concept applied to cybersecurity:
PracticalTopicPractical 01—Practical 02—Practical 03—Practical 04—Practical 05—Practical 06—Practical 07—Practical 08—Practical 09—Practical 10—

📄 References

M. M. Kontagora et al., "An Evaluation of ML Models for Threat Classification in IoT Devices," Open Access Library Journal, 2025
S. Baruah et al., "Enhanced P2P Botnet Detection Using Differential Evolution," Future Internet, 2025
J. Velasco-Mata et al., "Real-time botnet detection on large network bandwidths using ML," Scientific Reports, 2023
M. R. Asif et al., "Botnet detection in IoT using stacked ensemble learning," Scientific Reports, 2025



📄 License
All work in this repository is submitted as academic coursework at James Cook University. Not for redistribution.
