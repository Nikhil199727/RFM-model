# RFM-model
### Introduction
Imagine you run an online retail store and want to understand your customers better. Who are your best customers? Who is at risk of leaving? To answer these questions, this project uses RFM analysis — a method that measures customer value by looking at three key factors: **Recency** (how recently a customer made a purchase), **Frequency** (how often they purchase), and **Monetary value** (how much they spend). 

The goal is to analyze customer behavior, segment them based on their shopping habits, and discover actionable insights to drive more targeted marketing strategies. By applying RFM analysis to our dataset, we can identify high-value customers and potential opportunities for improvement.

### Dataset Description
The dataset was sourced from **Kaggle** and contains transactions of an online retail store. Below is a breakdown of the dataset based on the `.info()` method:

- **Type and Size**: 
  The dataset has around **500,000 rows** and **8 columns**. Each row corresponds to a transaction, and the columns represent details such as the invoice number, stock code, product description, quantity sold, invoice date, unit price, customer ID, and the customer's country.

- **Variables**:
  - `InvoiceNo`: Unique number assigned to each transaction.
  - `StockCode`: Unique product identifier.
  - `Description`: Description of the product.
  - `Quantity`: Number of units purchased in the transaction.
  - `InvoiceDate`: The date when the transaction occurred.
  - `UnitPrice`: The price per unit of the product.
  - `CustomerID`: Unique identifier for each customer.
  - `Country`: The country where the customer is located.

- **Data Quality**:
  - **Missing Values**: 
    The dataset had missing values in both the `CustomerID` and `Description` columns. All rows missing `CustomerID` were dropped, as they couldn’t be linked to any particular customer. Missing `Description` values were filled with "Unknown".
  - **Duplicates**: 
    Duplicate rows were identified and removed to avoid double-counting of transactions.
  - **Measurement Scales**:
    - **Nominal**: InvoiceNo, StockCode, Description, CustomerID, and Country.
    - **Numerical**: Quantity and UnitPrice.

### Objectives of the Project
The main objectives of this project include:
1. **Customer Segmentation**: Classify customers based on their purchasing behavior using the RFM approach.
2. **Identify Key Patterns**: Determine which customers are highly engaged and contribute the most revenue to the business.
3. **Generate Insights for Targeted Marketing**: Provide actionable insights to guide future marketing efforts by understanding customer loyalty and potential churn.

**Key Questions**:
- Which customers are frequent shoppers, and how much do they spend?
- How can we identify customers who have not made recent purchases and may be at risk of churning?
- What patterns exist between recency, frequency, and monetary value across different customer segments?

### Tools
- **Libraries Used**: 
  - `pandas` for data manipulation.
  - `numpy` for numerical calculations.
  - `seaborn` and `matplotlib` for data visualization.
  - `Prophet` for potential time series forecasting (though not used in the initial analysis).
  
- **Programming Language**: The entire analysis was conducted using **Python**.

### Insights

1. **RFM Table**:
   After cleaning the dataset and calculating the RFM metrics:
   - **Recency**: Measured by the number of days since the last purchase. The smaller the recency value, the more recent the customer's interaction.
   - **Frequency**: Indicates how many distinct transactions a customer has made.
   - **Monetary Value**: Represents the total spending of each customer over time.

   The merged RFM DataFrame provides a clear picture of each customer's buying behavior.

2. **Recency Distribution**:
   - The distribution shows a large number of customers have made recent purchases, indicating an active user base. However, a significant portion of customers have not made purchases in a long time, suggesting they may need re-engagement efforts.

3. **Frequency Distribution**:
   - Most customers have only made a few purchases, which is typical for many retail businesses. However, a smaller group of customers has made frequent purchases, representing the store's loyal, high-frequency shoppers.

4. **Monetary Distribution**:
   - The majority of customers fall into the low-to-moderate spending category. However, a few customers stand out, contributing a disproportionately high monetary value, emphasizing the 80/20 rule where a small percentage of customers contribute a large portion of the revenue.

![download](https://github.com/user-attachments/assets/be749fd8-77e5-491e-b1f8-1e63f08f09a9)

### Recommendations and Future Analysis

1. **Customer Retention Efforts**: 
   - The business should focus on re-engaging customers who have not made purchases recently. Email marketing campaigns or special offers targeting these customers could help bring them back.

2. **Loyalty Programs**: 
   - High-frequency and high-monetary-value customers should be rewarded with loyalty programs or personalized incentives to encourage repeat purchases and brand loyalty.

3. **Churn Prevention**:
   - Identifying customers with high recency and low frequency could help in creating targeted promotions aimed at preventing churn.

4. **Future Analysis**:
   - **Time Series Forecasting**: Using tools like Prophet, we can forecast future demand trends based on historical purchasing behavior. This could help the business in managing inventory and planning future marketing efforts.
   - **Customer Lifetime Value (CLV)**: A follow-up analysis could calculate the lifetime value of customers, providing further insights into how much revenue can be expected from each segment.
   - **A/B Testing for Offers**: Implement A/B tests to see which offers work best for different customer segments, especially those with lower recency and frequency.

By understanding customer behavior and utilizing the insights gained from RFM analysis, businesses can optimize their marketing strategies, increase retention, and ultimately drive growth.
