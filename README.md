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
> The visual above indicates that the majority of customers make fewer than two service calls. This trend suggests that there are relatively few issues, and when problems do arise, they are typically resolved within two or fewer calls.

![image](https://github.com/user-attachments/assets/4179a660-9043-4ae0-9404-94ef679c5529)
> The histogram represents the distribution of account lengths, ranging from 0 to 250. The data follows a normal distribution, peaking at around 90. This suggests that most accounts have a length close to 90, with fewer accounts having significantly shorter or longer durations.

![image](https://github.com/user-attachments/assets/1e8bab62-ed6c-485e-9da5-6de359381d9f)
> Most customers have total day charges between $25 and $37, with half of them below $31. While the charges are generally balanced, a few customers have unusually low or high charges, which are considered outliers.
![image](https://github.com/user-attachments/assets/3ec445f9-9b1d-4a41-b28e-bd6a4bd94319)
> The bar graph shows that customers with area code 415 make the most calls, with an average of about 16.2 calls. In comparison, area codes 408 and 510 each have around 800 calls, indicating a consistent but lower call frequency than 415.

## Bivariate 
In this section we will be investigating the relationship between 2 varaibles and how they are distributed in the dataset

![image](https://github.com/user-attachments/assets/035cbc64-98b7-4d1a-b5e2-562899b83a65)
The bar graph compares the total day charges between customers who use international services and those who don't. Both groups have similar charges, but customers who use international services have a slightly higher average, around 33. This suggests that international service usage slightly increases day charges.

![image](https://github.com/user-attachments/assets/4017b130-5119-4e21-8a28-9380e117e10f)
The bar graph shows that customers who have churned tend to have a higher average total day charge (about 65) compared to those who haven't churned (around 58). This suggests that customers who leave the service usually incur higher day charges.

























