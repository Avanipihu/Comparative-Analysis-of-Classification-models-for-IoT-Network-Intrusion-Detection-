# Comparative Analysis of Machine Learning Algorithms for IoT Network Intrusion Detection

## Project Overview

This project presents a comparative analysis of four supervised machine-learning classification algorithms: Naive Bayes, Support Vector Machine (SVM), Decision Tree, and Random Forest for detecting and classifying malicious network traffic in Internet of Things (IoT) environments. The experiment uses the RT-IoT2022 dataset, which contains normal network traffic and multiple types of cyberattacks. The primary objective is to identify the classifier that provides the best balance between classification performance, detection of less frequent attacks, and computational efficiency.

## Problem Statement

The increasing number of connected IoT devices has expanded the potential attack surface for cybercriminals. Traditional intrusion-detection systems may struggle to identify different types of attacks in heterogeneous IoT networks. This project investigates whether classical machine-learning algorithms can effectively distinguish normal network traffic from malicious activities such as DoS, DDoS, ARP poisoning, network scanning, and SSH brute-force attacks.

## Dataset

The RT-IoT2022 dataset is obtained from the UCI Machine Learning Repository. It contains 123,117 observations and 83 usable network-traffic features, including numerical and categorical attributes. The dataset includes normal IoT traffic and multiple malicious traffic categories, making it suitable for multiclass network intrusion detection.

## Methodology

The methodology begins with loading and exploring the dataset to understand its structure, feature distributions, and class imbalance. Irrelevant identifier columns are removed, categorical features are converted into numerical representations using one-hot encoding, and numerical features are standardized where required. The dataset is divided into training and testing sets using an 80:20 stratified split to preserve the approximate distribution of attack classes.

The four machine-learning algorithms are trained using the prepared dataset and evaluated on unseen test data. Hyperparameter tuning is performed for SVM, Decision Tree, and Random Forest using GridSearchCV. The models are compared using classification metrics and visualizations to identify their strengths and limitations.

## Machine Learning Algorithms

Naive Bayes uses Bayes' theorem to estimate the probability that a network-traffic observation belongs to a particular attack category. It provides a probabilistic classification approach based on the assumption that features are conditionally independent given the class.

Support Vector Machine identifies a decision boundary that separates different classes in the feature space. It can use linear or nonlinear kernels to classify complex network-traffic patterns and generally benefits from feature standardization.

Decision Tree classifies network traffic by recursively splitting observations according to feature values. It uses splitting criteria such as Gini impurity to form decision rules that distinguish normal and malicious traffic.

Random Forest combines multiple Decision Trees trained on different samples and feature subsets. The final prediction is determined through voting among the trees, helping improve robustness and reduce the variance associated with a single decision tree.

## Evaluation Metrics

The performance of the classifiers is assessed using accuracy, precision, recall, F1-score, macro-F1 score, ROC-AUC where applicable, and confusion matrices. Training time and prediction time are also considered to evaluate computational efficiency. Macro-averaged metrics are particularly important because the dataset contains unequal numbers of observations across attack categories. This helps ensure that the performance of less frequent attacks is considered alongside common attack classes.

## Tools and Technologies

Python is used as the primary programming language, with Jupyter Notebook serving as the development environment. Pandas and NumPy support data manipulation and numerical computation, while Scikit-learn provides the classification algorithms, preprocessing methods, hyperparameter tuning, and evaluation metrics. Matplotlib and Seaborn are used to generate visualizations and confusion matrices. The Ucimlrepo library can be used to retrieve the dataset from the UCI Machine Learning Repository.

## Results and Analysis

The experimental analysis compares the four classifiers using their classification metrics, confusion matrices, and computational requirements. The results are interpreted with particular attention to macro-F1 score, macro-recall, and the detection of minority attack classes rather than accuracy alone. The confusion matrices help identify attack categories that are correctly classified and those that are frequently misclassified. The final classifier should be selected based on the actual experimental results and the balance between detection performance and computational cost.

## Conclusion

This project demonstrates the application of classical machine-learning algorithms to multiclass IoT network intrusion detection using the RT-IoT2022 dataset. By applying data preprocessing, stratified train-test splitting, model training, hyperparameter tuning, and systematic evaluation, the experiment provides a structured comparison of Naive Bayes, SVM, Decision Tree, and Random Forest. It highlights the importance of considering class imbalance, macro-averaged evaluation metrics, and computational efficiency when selecting a suitable intrusion-detection classifier.

## Future Scope

Future improvements may include feature selection, class-imbalance handling through techniques such as SMOTE or class weighting, further hyperparameter optimization, and explainable AI methods such as SHAP. The study can also be extended by comparing the classical classifiers with advanced models such as XGBoost, LightGBM, neural networks, and autoencoders. Additional possibilities include real-time intrusion detection and cross-dataset validation to evaluate how well the trained models generalize to different IoT network environments.
