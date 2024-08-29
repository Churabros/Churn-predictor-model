# Moringa_phase3_project
Moringa_phase3_project
## Business Understanding
I have been commissioned by the Customer Retention Manager at SyriaTel to develop a binary classification model aimed at predicting customer churn. This model is essential for identifying customers at high risk of leaving the company, allowing SyriaTel to proactively address potential attrition. By analyzing the key factors contributing to churn, the Retention Manager can implement targeted strategies to enhance customer retention, thereby minimizing revenue loss and boosting long-term profitability. The insights generated from this model will be instrumental in shaping effective marketing campaigns and optimizing customer engagement efforts.

## Data Understanding

The dataset, sourced from [Kaggle](https://www.kaggle.com/becksddf/churn-in-telecoms-dataset), consists of 3,333 records from SyriaTel customers, capturing their service usage and interactions with the company. The primary objective is to use these features to predict customer churn, as indicated by the `churn` column.

### Feature Descriptions

- **`state`**: The U.S. state where the customer resides (categorical). This may help identify regional patterns in churn.
- **`account length`**: Duration of the customer's account in days (integer). Longer account lengths might correlate with lower churn rates.
- **`area code`**: Area code associated with the customer's phone number (integer). This may provide additional regional insights.
- **`phone number`**: Customer's phone number (categorical, treated as an identifier). Not used for prediction but helps in data management.
- **`international plan`**: Indicates if the customer has an international calling plan (categorical: "yes" or "no"). This may affect churn rates, as customers with international plans might have different usage patterns.
- **`voice mail plan`**: Indicates if the customer has a voice mail plan (categorical: "yes" or "no"). Voice mail plans could be associated with customer satisfaction and retention.
- **`number vmail messages`**: Number of voice mail messages received by the customer (integer). This may reflect customer engagement levels.
- **`total day minutes`**: Total minutes used by the customer during the day (float). High day usage might influence churn likelihood.
- **`total day calls`**: Total number of calls made by the customer during the day (integer). This complements the `total day minutes` in assessing usage patterns.
- **`total day charge`**: Total charges for daytime calls (float). Helps to understand the financial impact of customer usage.
- **`total eve minutes`**: Total minutes used by the customer in the evening (float). Evening usage patterns may provide additional insights into customer behavior.
- **`total eve calls`**: Total number of calls made by the customer in the evening (integer). Useful for analyzing call frequency and usage.
- **`total eve charge`**: Total charges for evening calls (float). Complements the `total eve minutes` in understanding usage patterns.
- **`total night minutes`**: Total minutes used by the customer at night (float). Nighttime usage patterns may also impact churn.
- **`total night calls`**: Total number of calls made by the customer at night (integer). Provides insights into usage patterns during off-peak hours.
- **`total night charge`**: Total charges for nighttime calls (float). Helps to understand the financial aspects of nighttime usage.
- **`total intl minutes`**: Total number of international minutes used by the customer (float). International usage may be a factor in churn.
- **`total intl calls`**: Total number of international calls made by the customer (integer). Complements the `total intl minutes` in understanding international usage patterns.
- **`total intl charge`**: Total charges for international calls (float). Provides insight into the cost associated with international calls.
- **`customer service calls`**: Number of calls made by the customer to customer service (integer). High numbers may indicate dissatisfaction or issues, potentially leading to churn.
- **`churn`**: Boolean indicator of whether the customer has discontinued their service (target variable). This is the outcome variable we aim to predict.

# EDA
Now that the data is cleaned and preprocessed we will start analysising the data in three diffrent phases 
## Univariate
In this section we will be investigating the individual varaibles and how they are distributed in the dataset
![image](https://github.com/user-attachments/assets/edfab31a-278e-4633-9306-f16c0ec7dca3)

The visual above indicates that the majority of customers make fewer than two service calls. This trend suggests that there are relatively few issues, and when problems do arise, they are typically resolved within two or fewer calls.

![image](https://github.com/user-attachments/assets/4179a660-9043-4ae0-9404-94ef679c5529)

The histogram represents the distribution of account lengths, ranging from 0 to 250. The data follows a normal distribution, peaking at around 90. This suggests that most accounts have a length close to 90, with fewer accounts having significantly shorter or longer durations.

![image](https://github.com/user-attachments/assets/1e8bab62-ed6c-485e-9da5-6de359381d9f)

 Most customers have total day charges between $25 and $37, with half of them below $31. While the charges are generally balanced, a few customers have unusually low or high charges, which are considered outliers.
![image](https://github.com/user-attachments/assets/3ec445f9-9b1d-4a41-b28e-bd6a4bd94319)

The bar graph shows that customers with area code 415 make the most calls, with an average of about 16.2 calls. In comparison, area codes 408 and 510 each have around 800 calls, indicating a consistent but lower call frequency than 415.

## Bivariate 
In this section we will be investigating the relationship between 2 varaibles and how they are distributed in the dataset

![image](https://github.com/user-attachments/assets/035cbc64-98b7-4d1a-b5e2-562899b83a65)
The bar graph compares the total day charges between customers who use international services and those who don't. Both groups have similar charges, but customers who use international services have a slightly higher average, around 33. This suggests that international service usage slightly increases day charges.

![image](https://github.com/user-attachments/assets/4017b130-5119-4e21-8a28-9380e117e10f)
The bar graph shows that customers who have churned tend to have a higher average total day charge (about 65) compared to those who haven't churned (around 58). This suggests that customers who leave the service usually incur higher day charges.

# Modeling
In this phase we will our classification modeling using 2 diffrent models (`logestic regression` and `decesion trees`)

## Best Logestic regression 

![image](https://github.com/user-attachments/assets/4f61d19e-a125-4edc-bb1d-63acf6bf174b)
**Accuracy**: 86%  
The model correctly predicted 86% of the test cases.

**Classification Report**:  
- **False Class (Not Churned)**:
  - **Precision**: 87%
  - **Recall**: 98%
  - **F1-Score**: 92%

- **True Class (Churned)**:
  - **Precision**: 58%
  - **Recall**: 19%
  - **F1-Score**: 28%

**Summary**:  
The model performs well at predicting non-churned customers but struggles with churned customers. The imbalance between the two classes is likely affecting its performance on the minority class.



## Best Decesion Tree

![image](https://github.com/user-attachments/assets/64f1f3da-f682-4b09-89a0-74a4cc13d046)

### Model Evaluation Summary

**Accuracy**: 97.90%  
The model achieved an accuracy of 97.90%, meaning it correctly predicted the outcome for 97.90% of the test cases.

**Classification Report**:

- **False Class (Not Churned)**:
  - **Precision**: 98% – The model correctly identified 98% of non-churned instances.
  - **Recall**: 100% – It detected 100% of actual non-churned cases.
  - **F1-Score**: 99% – Indicates excellent performance in predicting non-churned customers.

- **True Class (Churned)**:
  - **Precision**: 99% – The model correctly identified 99% of churned instances.
  - **Recall**: 87% – It detected 87% of actual churned cases.
  - **F1-Score**: 93% – Shows strong performance in predicting churned customers.


# Evaluating
In this section, we compare the performance of the baseline logistic regression model and the best decision tree model based on various evaluation metrics.

### Model Comparison: Logistic Regression vs. Decision Tree


#### **Logistic Regression Model (Baseline)**

- **Accuracy**: 86%

**Classification Report:**

| Metric                | False (Not Churned) | True (Churned) | Average (Macro) | Average (Weighted) |
|-----------------------|---------------------|----------------|-----------------|---------------------|
| **Precision**         | 87%                 | 58%            | 72%             | 83%                 |
| **Recall**            | 98%                 | 19%            | 58%             | 86%                 |
| **F1-Score**          | 92%                 | 28%            | 60%             | 82%                 |

**Confusion Matrix:**

|                     | Predicted False | Predicted True |
|---------------------|-----------------|----------------|
| **Actual False**    | 565             | 1              |
| **Actual True**     | 13              | 88             |

- **Strengths**:
  - High recall for the `False` class (98%) means it effectively identifies non-churned customers.
  - Good precision for the `False` class (87%) reduces the number of false positives.

- **Weaknesses**:
  - Lower recall for the `True` class (19%) indicates it misses many churned customers.
  - Precision and F1-Score for the `True` class are relatively low, showing weaker performance in identifying churned customers.

---

#### **Decision Tree Model (Best with Hyperparameter Tuning)**

- **Accuracy**: 97.90%

**Classification Report:**

| Metric                | False (Not Churned) | True (Churned) | Average (Macro) | Average (Weighted) |
|-----------------------|---------------------|----------------|-----------------|---------------------|
| **Precision**         | 98%                 | 99%            | 98%             | 98%                 |
| **Recall**            | 100%                | 87%            | 93%             | 98%                 |
| **F1-Score**          | 99%                 | 93%            | 96%             | 98%                 |

**Confusion Matrix:**

|                     | Predicted False | Predicted True |
|---------------------|-----------------|----------------|
| **Actual False**    | 565             | 1              |
| **Actual True**     | 13              | 88             |

- **Strengths**:
  - Very high accuracy (97.90%) and strong performance in precision, recall, and F1-Score for both classes.
  - Excellent recall for the `False` class (100%) and high recall for the `True` class (87%) indicate effective identification of both churned and non-churned customers.

- **Weaknesses**:
  - Minor trade-off in precision for the `True` class compared to recall, but overall performance is very strong.

---

### **Comparison Summary**

- **Accuracy**: The decision tree model significantly outperforms the logistic regression model (97.90% vs. 86%).

- **Precision**: The decision tree model has higher precision for both classes, particularly for the `True` class (99% vs. 58%).

- **Recall**: The decision tree model has higher recall for both classes, with a notable improvement in the `True` class (87% vs. 19%).

- **F1-Score**: The decision tree model has a better F1-Score for both classes, reflecting a better balance between precision and recall.

**Conclusion**: The decision tree model, after hyperparameter tuning, is superior in terms of accuracy, precision, recall, and F1-Score. It provides a significantly better overall performance compared to the logistic regression model, making it more suitable for accurately identifying both churned and non-churned customers in this dataset.


# Limitations
1. **Class Imbalance**: The dataset exhibits a significant class imbalance between the churned (`True`) and non-churned (`False`) classes. This imbalance can lead to biased model performance, where the model may perform well on the majority class (non-churned) but poorly on the minority class (churned).

2. **Feature Relevance and Data Quality**: Some features in the dataset, such as `state` and `area_code`, may have limited relevance to the target variable (churn). Including irrelevant features can introduce noise and affect model performance. Additionally, missing or inaccurate data entries could impact the quality of predictions.

3. **Overfitting Risk**: The decision tree model, particularly after hyperparameter tuning, shows very high accuracy. However, such high performance could indicate overfitting, where the model performs exceptionally well on the training and test datasets but may not generalize effectively to unseen data.

4. **Model Interpretability**: The decision tree model, while effective, can become complex and less interpretable with extensive hyperparameter tuning. This complexity might make it challenging to understand and explain the decision-making process, which can be a drawback for deployment in real-world applications where model transparency is crucial.

5. **Performance Variability**: The performance of the models may vary with different subsets of data or if the data distribution changes over time. This variability can affect the reliability of the model when used in production, leading to potential issues if the model encounters data that significantly deviates from the training data.

# Findings 
 
1. **Logistic Regression Models**: Several iterations of logistic regression models, including those with SMOTE and over/under sampling, did not achieve satisfactory performance. These methods did not effectively address the class imbalance, resulting in lower accuracy and performance issues.

2. **Decision Tree Performance**: A baseline decision tree model, without hyperparameter tuning, performed better than the logistic regression models but was outperformed by a more advanced decision tree model.

3. **Tuned Decision Tree Model**: The decision tree model with hyperparameter tuning and grid search emerged as the best performer. It significantly outperformed both the logistic regression models and the untuned decision tree, demonstrating its effectiveness in addressing the churn prediction problem.

# Recommendations 
1. **Enhance Customer Retention Strategies:**

Given the decision tree model’s high accuracy in predicting customer churn, it is advisable to leverage these insights to craft effective retention strategies. Focus on identifying customers at high risk of leaving and deploy targeted initiatives such as personalized offers, loyalty programs, or enhanced customer support. By doing so, you can more effectively address the needs of at-risk customers, potentially reducing churn and fostering greater customer loyalty.

2. **Optimize Features and Pricing Plans:**

The logistic regression model highlights the impact of class imbalance and feature relevance on performance. To address these issues, consider refining features such as customer service interactions and reviewing pricing strategies. For instance, if higher charges are linked to increased churn, introducing discounts or flexible pricing for high-charging customers could be beneficial. Adjusting service plans based on usage patterns may also help in retaining more customers.

3. **Regularly Update Models:**

To maintain the accuracy and relevance of your models, implement a routine for regular updates. Customer behavior and market conditions can shift over time, which may affect model performance. Periodically retrain the models with new data and revise features as necessary to ensure that your predictions remain reliable and aligned with current trends. This proactive approach will help in adapting to changes and maintaining effective customer retention strategies.

















