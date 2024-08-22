# Credit Card Fraud Detection

## Project Overview

<p align="justify">
The goal of this project is to develop a robust system for detecting fraudulent credit card transactions. Given the highly imbalanced nature of the dataset, where fraudulent transactions are a small fraction of the total, this presents a significant challenge.

To tackle this, three machine learning algorithms were employed: Logistic Regression, Random Forest, and Decision Tree. Logistic Regression was selected for its simplicity and interpretability, providing a reliable baseline. Random Forest, an ensemble method, enhances prediction accuracy by aggregating multiple decision trees, while the Decision Tree model offers clear and interpretable decision-making processes.

Due to the extreme imbalance in the dataset, where fraudulent transactions are vastly outnumbered by non-fraudulent ones, specialized techniques were necessary to prevent model bias towards the majority class. SMOTE (Synthetic Minority Over-sampling Technique) was applied to generate synthetic samples for the minority class, thereby balancing the class distribution and improving the models’ ability to detect fraudulent transactions effectively.

By integrating these models and employing advanced techniques to manage class imbalance, the project aims to deliver a highly effective solution for credit card fraud detection, ensuring both accuracy and reliability.

</p>

## Table of Contents

- [Project Overview](#project-overview)
- [About the Dataset](#about-the-dataset)
- [Results](#results)
  - [Classification Reports](#classification-reports)
  - [Confusion Matrix](#confusion-matrix)
  - [Performance Metrics](#performance-metrics)
- [Conclusion](#conclusion)
- [License](#license)

## About the Dataset

This project uses a dataset from [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud), which includes credit card transactions from European cardholders in September 2013. The dataset contains 284,807 transactions over two days, with 492 transactions labeled as fraudulent, representing a class imbalance with fraudulent transactions making up just 0.172% of the total.

- Features: The dataset contains numerical variables derived from Principal Component Analysis (PCA). Due to confidentiality constraints, the original features are not available. The dataset features include:

  - V1, V2, ..., V28: Principal components resulting from PCA.
  - Time: The number of seconds elapsed between each transaction and the first transaction in the dataset.
  - Amount: The transaction amount, which can be used for cost-sensitive learning.
  - Class: The target variable indicating whether a transaction is fraudulent (1) or non-fraudulent (0).

## Results

### Classification Reports

The classification reports for each model are detailed below:

#### Logistic Regression

```
              precision    recall  f1-score   support

           0       0.94      0.98      0.96     85149
           1       0.98      0.94      0.96     85440

    accuracy                           0.96    170589
   macro avg       0.96      0.96      0.96    170589
weighted avg       0.96      0.96      0.96    170589
```

#### Decision Tree

```
              precision    recall  f1-score   support

           0       1.00      1.00      1.00     85149
           1       1.00      1.00      1.00     85440

    accuracy                           1.00    170589
   macro avg       1.00      1.00      1.00    170589
weighted avg       1.00      1.00      1.00    170589
```

#### Random Forest

```
              precision    recall  f1-score   support

           0       1.00      1.00      1.00     85149
           1       1.00      1.00      1.00     85440

    accuracy                           1.00    170589
   macro avg       1.00      1.00      1.00    170589
weighted avg       1.00      1.00      1.00    170589
```

### Confusion Matrix

The confusion matrices for each model are shown below:

#### Logistic Regression

|                  | Predicted Non-Fraud | Predicted Fraud |
| ---------------- | ------------------- | --------------- |
| Actual Non-Fraud | 83595               | 1554            |
| Actual Fraud     | 5304                | 80136           |

#### Decision Tree

|                  | Predicted Non-Fraud | Predicted Fraud |
| ---------------- | ------------------- | --------------- |
| Actual Non-Fraud | 84881               | 268             |
| Actual Fraud     | 85                  | 85355           |

#### Random Forest

|                  | Predicted Non-Fraud | Predicted Fraud |
| ---------------- | ------------------- | --------------- |
| Actual Non-Fraud | 85133               | 16              |
| Actual Fraud     | 0                   | 85440           |

### Performance Metrics

The following table summarizes the performance of each model using key metrics: accuracy, precision, recall, and F1-score.

| Model               | Accuracy | Precision | Recall | F1-score |
| ------------------- | -------- | --------- | ------ | -------- |
| Logistic Regression | 0.9598   | 0.9810    | 0.9379 | 0.9590   |
| Decision Tree       | 0.9979   | 0.9969    | 0.9990 | 0.9979   |
| Random Forest       | 0.9999   | 0.9998    | 1.0000 | 0.9999   |

- Accuracy: The proportion of total correct predictions (both fraud and non-fraud).
- Precision: The proportion of true positive predictions out of all positive predictions made by the model.
- Recall: The proportion of true positive predictions out of all actual positive instances.
- F1-score: The harmonic mean of precision and recall, providing a single metric to evaluate model performance

## Conclusion

<p align="justify">
After evaluating the performance of Logistic Regression, Decision Tree, and Random Forest models, the Random Forest algorithm has emerged as the most effective for detecting fraudulent credit card transactions in this dataset. The Random Forest model demonstrated exceptional performance, achieving an accuracy of 99.99%, precision of 99.98%, recall of 100.00%, and an F1-score of 99.99%. These results indicate that Random Forest not only accurately classifies transactions but also effectively identifies fraudulent activities with minimal false positives.

In contrast, while both the Decision Tree and Logistic Regression models also performed well, they did not reach the same level of accuracy and precision as the Random Forest model. The Decision Tree model achieved an accuracy of 99.79% and the Logistic Regression model achieved 95.98%. The superior performance of Random Forest in this context highlights its robustness and capability to handle class imbalance effectively, making it the optimal choice for this credit card fraud detection system.

</p>

## License

This project is licensed under the MIT License - see the [LICENSE](./LICENSE) file for details.
