# Predictive-Analytics-for-Supermarket-Sales
![inventory](https://github.com/MeiLing19/Predictive-Analytics-for-Supermarket-Sales/blob/main/Inventory.jpg)

## Project Domain
This project focuses on analyzing supermarket sales. A deep understanding of sales patterns in supermarkets is crucial for management to optimize marketing strategies, inventory management, and customer experience.
### Background
In the retail industry, especially in supermarkets, the ability to accurately predict sales is paramount for effective business operations and strategic decision-making. 
Sales prediction involves forecasting future sales volumes based on historical data, market trends, and various external factors. 
This predictive analytics process plays a crucial role in optimizing inventory management, staffing levels, and revenue forecasting.

### Why it is need to be solved?
1. **Inventory Management**: Maintaining the right balance of inventory is essential to meet customer demand while minimizing carrying costs and the risk of stockouts. Accurate sales predictions help supermarkets anticipate demand for different products and adjust their inventory levels accordingly.
2. **Staffing Optimization**: Proper staffing levels are essential for ensuring excellent customer service and operational efficiency. By accurately forecasting sales, supermarkets can schedule their staff appropriately to meet customer demand during peak hours while avoiding overstaffing during slower periods.
3. **Revenue Forecasting**: Reliable sales forecasts enable supermarkets to estimate future revenue streams accurately. This information is vital for budgeting, financial planning, and setting realistic business goals. It also helps in identifying opportunities for revenue growth and expansion.
4. **Customer Satisfaction**: Predictive analytics in sales forecasting contributes to enhancing customer satisfaction by ensuring that the right products are available at the right time. Satisfied customers are more likely to return, leading to increased loyalty and higher retention rates.
5. **Profitability**: Ultimately, accurate sales predictions translate into higher profitability for supermarkets. By optimizing inventory levels, reducing carrying costs, and maximizing revenue potential, supermarkets can improve their bottom line and remain competitive in the market.

## Business Understanding
### Problem Statements
1. Inaccurate sales forecasts lead to overstocking or understocking of products.
2. Manual forecasting methods are time-consuming and prone to errors.
### Goals
1. Develop a predictive model to forecast supermarket sales accurately.
2. Reduce inventory costs by optimizing stocking levels based on demand predictions.
### Solution Statements
1. Implement linear regression and decision tree regression algorithms to predict sales.
2. Fine-tune model parameters using hyperparameter tuning to improve accuracy.

## Data Understanding
### Dataset
[Source](https://www.kaggle.com/code/mhmdkardosha/market-analysis/input)
Supermarket sales data including features like unit price, quantity, tax, branch, city, customer type, etc.
### Number of records
1000 rows × 17 columns
### Data Condition
Clean, no missing values.
### Variabel
The variables in the Supermarket Sales dataset are as follows :
- Unit price: the unit price of the product
- Quantity: the number of products purchased
- Tax 5%: 5% tax on the total price
- Total: total purchase price
- cogs: cost of goods sold
- gross margin percentage: gross margin percentage
- gross income: gross income
- Rating: rating of a product by a customer
- Branch_A, Branch_B, Branch_C: supermarket store branches.
- City_Mandalay, City_Naypyitaw, City_Yangon: the city where the supermarket store is located.
- Customer type_Member, Customer type_Normal: customer type (member or non-member)
- Gender_Female, Gender_Male: the gender of the customer.
- Product line_Electronic accessories, Product line_Fashion accessories, Product line_Food and beverages, Product line_Health and beauty, Product line_Home and lifestyle, Product line_Sports and travel: type of product.
- Payment_Cash, Payment_Credit card, Payment_Ewallet: payment method

## Data Preparation
At this stage, the raw data obtained from the source will be processed so that it becomes ready to be used in modeling.
### Identifying and Displaying the Number of Missing Values

missing_values = data.isnull().sum()

- The isnull() method checks for missing values in the dataset, and the sum() function calculates the total number of missing values for each column.
print(missing_values)
- The variable missing_values contains the sum of missing values for each column. Printing missing_values provides a summary of the number of missing values in each column of the dataset

**Output** :
Invoice ID                 0
Branch                     0
City                       0
Customer type              0
Gender                     0
Product line               0
Unit price                 0
Quantity                   0
Tax 5%                     0
Total                      0
Date                       0
Time                       0
Payment                    0
cogs                       0
gross margin percentage    0
gross income               0
Rating                     0
dtype: int64

- Based on the output, there are no null or NaN values in the dataset as the number is zero for each column.
Therefore, no additional steps are needed to handle missing values in the data cleaning stage.
The data is clean and ready to be used for further analysis.

## Modeling

### Linear Regression
**Modeling Stages**
- Splitting the data into features (X) and targets (y).
- Dividing data into training data and test data.
- Creating a Linear Regression model.
- Training the model using training data.
- Testing the model using test data.
  
**Parameters Used**
  fit_intercept (default=True)
- Specifies whether to calculate the intercept (b) in the linear regression model. If set False, the regression line will pass through the point (0,0).
  normalize (default=False)
  Specifies whether the features will be normalized before regression. Normalization is done by subtracting the mean and dividing by the standard deviation of each feature.
  
**Advantages**
- Simple and easy to interpret.
- Suitable for cases where the relationship between features and targets is linear.
  
**Disadvantages**
- Vulnerable to linearity and independence assumptions.
- Ineffective in handling non-linear relationships between features and targets.

## Decision Trees Regression
**Modeling Stages**
- Splitting the data into features (X) and targets (y).
- Dividing data into training data and test data.
- Creating a Decision Tree Regression model.
- Training the model using training data.
- Testing the model using test data.
  
**Parameters Used**
  random_state=42
- This parameter is used to specify the seed used in randomizing the process in the algorithm.
Setting the random_state value will ensure that the results are consistent each time the code is run.

**Advantages**
- Can handle non-linear relationships between features and targets.
- Easy to understand and interpret.
  
**Disadvantages**
- Prone to overfitting especially if not well organized.
- Unstable, small changes in data can result in very different trees.

## Evaluation
In this project, the evaluation metrics used are Mean Squared Error (MSE), Mean Absolute Error (MAE), and R-squared Score (R^2).
1. **Mean Squared Error (MSE)**
   MSE measures the average of the squares of the differences between the predicted values and the actual values.
   The formula for MSE is :
   ![mse](https://www.google.com/url?sa=i&url=https%3A%2F%2Fdeepchecks.com%2Fglossary%2Fmean-square-error-mse%2F&psig=AOvVaw0nGJsWozGqw3dR3d1qnj8b&ust=1710916335692000&source=images&cd=vfe&opi=89978449&ved=0CBMQjRxqFwoTCLjMrJXa_4QDFQAAAAAdAAAAABAE)
   MSE provides information about how close the average prediction is to the actual value. A lower MSE value indicates better model performance.
2. **Mean Absolute Error (MAE)**
   MAE measures the average of the absolute values of the differences between the predicted values and the actual values.
   The formula for MAE is:
   ![mae](https://www.google.com/url?sa=i&url=https%3A%2F%2Fmedium.com%2Ftrusted-data-science-haleon%2Fmape-vs-mae-which-metric-is-better-68dd559cbfb1&psig=AOvVaw2e-buvZ3PalC5yDVaqSDm4&ust=1710916507739000&source=images&cd=vfe&opi=89978449&ved=0CBMQjRxqFwoTCKiBr-fa_4QDFQAAAAAdAAAAABAE)
   MAE also provides information about how close the average prediction is to the actual value, but it is not affected by the square of the differences, making it more tolerant to outliers.
3. **R-squared Score (R^2)**
   R-squared measures how well the variability in the data is explained by the model. The R-squared value ranges from 0 to 1, where 1 indicates that the model perfectly fits the data.
   The formula for R-squared is:
   ![r^2](https://www.google.com/url?sa=i&url=https%3A%2F%2Fmedium.com%2F%40iliyafaramarzi1384%2Fwhat-is-r2-and-how-it-gets-negative-e927011d92ed&psig=AOvVaw2GxOXmLWFfra2mxj7knb78&ust=1710916587904000&source=images&cd=vfe&opi=89978449&ved=0CBMQjRxqFwoTCJjr0I3b_4QDFQAAAAAdAAAAABAE)
   R-squared provides the percentage of variability in the dependent variable that can be explained by the model. The closer the R-squared value is to 1, the better the model.
   
In evaluating the project results, we will review the values of MSE, MAE, and R^2 to understand how well our model predicts supermarket sales. Interpreting these values will provide insights into the model's performance in estimating sales.

## Result
**Linear Regression**
- Mean Squared Error (MSE): 2.56 × 10^-26
  Very close to zero, indicating the model's near-perfect prediction capability.
- Mean Absolute Error (MAE): 1.28×10^-13
  Very small, indicating high precision in predicting the data
- R-squared Score (R^2): 1.0
  1.0, indicating the model's ability to explain all the variability in the data

**Decision Trees Regressions**
- Mean Squared Error (MSE): 2.34
  Larger than Linear Regression, indicating more variability in the predicted data
- Mean Absolute Error (MAE): 0.92
  Larger than Linear Regression, indicating slightly lower accuracy in predicting the data
- R-squared Score (R^2):  0.99996
  Very close to 1.0, indicating excellent model fit to the data, although slightly lower than Linear Regression

## Conclusion
Based on this evaluation, the Linear Regression model seems more suitable for predicting Supermarket Sales dataset due to its slightly better performance. 
Although the Decision Tree Regressor provides excellent results, Linear Regression demonstrates higher accuracy with lower error values and a perfect R-squared score. 
Therefore, the Linear Regression model can be considered the primary choice for predicting supermarket sales.
