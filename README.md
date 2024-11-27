<h1 style="color:red" align="center"><b>Market Segmentation Using Credit Card Data</b></h1>
<a href="Image.jpeg" target="_blank">
    <img src="Customer_Segmentation.jpeg" alt="Customer Segmentation Using K-Meansl" width="800" />
</a>

# **Overview**

### **Objective:**
The goal of this project is to perform customer segmentation using credit card data in order to provide targeted recommendations such as saving plans, loans, and wealth management services for different customer groups.

### **Data Description:**
This dataset contains the usage behavior of approximately 9,000 active credit card holders over a period of 6 months. It includes 18 behavioral variables that provide insights into the spending and payment habits of customers.

### **Data Source:**
The dataset can be downloaded from Kaggle using the following link:  
[Download Credit Card Data](https://www.kaggle.com/arjunbhasin2013/ccdata)

### **Attribute Information:**
The dataset includes the following attributes:
- **CUSTID:** Identification of the credit card holder (Categorical)
- **BALANCE:** The remaining balance available for purchases
- **BALANCEFREQUENCY:** Frequency of balance updates, with a score between 0 and 1 (1 = frequently updated, 0 = infrequently updated)
- **PURCHASES:** The total amount of purchases made from the account
- **ONEOFFPURCHASES:** The maximum purchase amount made in a single transaction
- **INSTALLMENTSPURCHASES:** The amount of purchases made in installments
- **CASHADVANCE:** The amount of cash advance provided to the customer
- **PURCHASESFREQUENCY:** Frequency of purchases, with a score between 0 and 1
- **ONEOFFPURCHASESFREQUENCY:** Frequency of one-off purchases, with a score between 0 and 1
- **PURCHASESINSTALLMENTSFREQUENCY:** Frequency of installment purchases, with a score between 0 and 1
- **CASHADVANCEFREQUENCY:** Frequency of cash advance transactions, with a score between 0 and 1
- **CASHADVANCETRX:** Number of transactions involving cash advances
- **PURCHASESTRX:** Number of purchase transactions made
- **CREDITLIMIT:** The credit limit available for the customer
- **PAYMENTS:** The amount paid by the customer towards their credit card balance
- **MINIMUM_PAYMENTS:** The minimum payment amount made by the customer
- **PRCFULLPAYMENT:** Percentage of the balance fully paid by the customer
- **TENURE:** The number of years the customer has had the credit card

---

# **Data Cleaning and Preprocessing**

- **Handling Missing Data:**  
  Missing values for the `MINIMUM_PAYMENTS` and `CREDIT_LIMIT` columns were filled with the median of the respective columns.

- **Outlier Detection:**  
  Outliers in numerical features such as `BALANCE`, `CREDIT_LIMIT`, and `PAYMENTS` were identified using the Interquartile Range (IQR) method. Outliers were removed from the dataset to avoid biasing the results.

- **Data Scaling:**  
  The features were scaled using the StandardScaler to normalize the data before applying clustering algorithms.

---

# **Customer Segmentation**

The dataset was subjected to **K-Means clustering** to segment the customers into distinct groups based on their spending and payment behaviors.

### **Optimal Number of Clusters (K):**
The optimal number of clusters was determined using the **Elbow Method**, which showed that 4 clusters is the most appropriate choice for segmentation.

### **Cluster Descriptions:**

1. **Cluster 1: Transactors**  
   - These are customers who pay off their credit card balance in full regularly.  
   - **Characteristics:**  
     - Low balance (~$104)  
     - Low cash advance usage (~$303)  
     - High percentage of full payment (23%)  
     - These customers are the least risky and are careful with their finances.

2. **Cluster 2: Revolvers**  
   - These customers treat their credit card as a loan.  
   - **Characteristics:**  
     - High balance (~$5000)  
     - High cash advance usage (~$5000)  
     - Low purchase frequency  
     - High cash advance frequency (0.5)  
     - Low percentage of full payments (3%)  
     - These customers are the most lucrative for credit card companies but are at higher risk due to the outstanding balance.

3. **Cluster 3: VIP/Prime Customers**  
   - High-value customers with large credit limits and good payment behaviors.  
   - **Characteristics:**  
     - High credit limit (~$16,000)  
     - Highest percentage of full payments  
     - These customers are ideal for targeted marketing, offering higher credit limits, and encouraging increased spending.

4. **Cluster 4: Low Tenure Customers**  
   - Customers who have recently joined and have not yet fully engaged with their credit card services.  
   - **Characteristics:**  
     - Low balance  
     - Low tenure (~7 years)  
     - These customers may require more engagement and education about credit usage.

---

# **Cluster Analysis and Insights:**
- **Cluster 1 (Transactors):** These customers make full payments regularly and are financially responsible. They have the lowest risk and can be targeted with savings plans or credit rewards.
- **Cluster 2 (Revolvers):** This group carries high balances and frequently uses cash advances, making them high-risk customers. They can be targeted with loan offers but need careful monitoring.
- **Cluster 3 (VIP/Prime):** These customers are ideal candidates for premium services, such as increasing credit limits or offering exclusive rewards. They exhibit good payment behavior and are less risky.
- **Cluster 4 (Low Tenure):** These customers have not been with the company for long and have lower balances. They could be targeted with educational campaigns on credit usage and responsible spending.

---

# **Model Deployment and Outcome**

The KMeans clustering model was saved and is available for further use:
- **Model File:** [kmeans_model.pkl](#)
- **Clustered Data:** [Clustered_Customer_Data.csv](#)

### **Conclusion:**
This segmentation helps identify distinct customer groups based on their credit card behavior. Each group has different needs and behaviors, which can be addressed with tailored financial products and services. By understanding customer segments, credit card companies can enhance their offerings, improve customer satisfaction, and reduce financial risk.

---

### **Files Available in this Repository:**
- **KMeans Model:** `kmeans_model.pkl`
- **Clustered Customer Data:** `Clustered_Customer_Data.csv`

---

You can view and download the segmented customer data and model from this repository.

---


