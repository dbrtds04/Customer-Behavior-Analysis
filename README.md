# Customer Shopping Behavior Analysis

## 📌 Project Overview

This project analyzes customer shopping behavior using transactional data from **3,900 purchases** across various product categories.

The goal is to uncover insights into:

- Spending patterns
- Customer segments
- Product preferences
- Subscription behavior

These insights can be used to guide strategic business decisions.

---

## 📊 Dataset Summary

| Attribute | Details |
|---|---|
| Rows | 3,900 |
| Columns | 18 |
| Missing Data | 37 values in `Review Rating` |

### Key Features

#### Customer Demographics
- Age
- Gender
- Location
- Subscription Status

#### Purchase Details
- Item Purchased
- Category
- Purchase Amount
- Season
- Size
- Color

#### Shopping Behavior
- Discount Applied
- Promo Code Used
- Previous Purchases
- Frequency of Purchases
- Review Rating
- Shipping Type

---

## 🐍 Exploratory Data Analysis using Python

The project began with data preparation and cleaning in Python.

### Data Loading

Imported the dataset using **Pandas**.

### Initial Exploration

Used:

```python
df.info()
```

to inspect the dataset structure and:

```python
df.describe()
```

to obtain summary statistics.
<div>

<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>Customer ID</th>
      <th>Age</th>
      <th>Gender</th>
      <th>Item Purchased</th>
      <th>Category</th>
      <th>Purchase Amount (USD)</th>
      <th>Location</th>
      <th>Size</th>
      <th>Color</th>
      <th>Season</th>
      <th>Review Rating</th>
      <th>Subscription Status</th>
      <th>Shipping Type</th>
      <th>Discount Applied</th>
      <th>Promo Code Used</th>
      <th>Previous Purchases</th>
      <th>Payment Method</th>
      <th>Frequency of Purchases</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>3900.000000</td>
      <td>3900.000000</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900.000000</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3863.000000</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900</td>
      <td>3900.000000</td>
      <td>3900</td>
      <td>3900</td>
    </tr>
    <tr>
      <th>unique</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2</td>
      <td>25</td>
      <td>4</td>
      <td>NaN</td>
      <td>50</td>
      <td>4</td>
      <td>25</td>
      <td>4</td>
      <td>NaN</td>
      <td>2</td>
      <td>6</td>
      <td>2</td>
      <td>2</td>
      <td>NaN</td>
      <td>6</td>
      <td>7</td>
    </tr>
    <tr>
      <th>top</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>Male</td>
      <td>Blouse</td>
      <td>Clothing</td>
      <td>NaN</td>
      <td>Montana</td>
      <td>M</td>
      <td>Olive</td>
      <td>Spring</td>
      <td>NaN</td>
      <td>No</td>
      <td>Free Shipping</td>
      <td>No</td>
      <td>No</td>
      <td>NaN</td>
      <td>PayPal</td>
      <td>Every 3 Months</td>
    </tr>
    <tr>
      <th>freq</th>
      <td>NaN</td>
      <td>NaN</td>
      <td>2652</td>
      <td>171</td>
      <td>1737</td>
      <td>NaN</td>
      <td>96</td>
      <td>1755</td>
      <td>177</td>
      <td>999</td>
      <td>NaN</td>
      <td>2847</td>
      <td>675</td>
      <td>2223</td>
      <td>2223</td>
      <td>NaN</td>
      <td>677</td>
      <td>584</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>1950.500000</td>
      <td>44.068462</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>59.764359</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.750065</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>25.351538</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>std</th>
      <td>1125.977353</td>
      <td>15.207589</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>23.685392</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>0.716983</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>14.447125</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1.000000</td>
      <td>18.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>20.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>2.500000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>1.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>975.750000</td>
      <td>31.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>39.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.100000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>13.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>1950.500000</td>
      <td>44.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>60.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>3.800000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>25.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2925.250000</td>
      <td>57.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>81.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>4.400000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>38.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
    <tr>
      <th>max</th>
      <td>3900.000000</td>
      <td>70.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>100.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>5.000000</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>50.000000</td>
      <td>NaN</td>
      <td>NaN</td>
    </tr>
  </tbody>
</table>
</div>

### Missing Data Handling

Checked for null values and imputed missing values in the `Review Rating` column using the **median rating of each product category**.

### Column Standardization

Renamed columns to **snake_case** for improved readability and documentation.

### Feature Engineering

Created the following features:

- `age_group` — created by binning customer ages.
- `purchase_frequency_days` — created from purchase data.

### Data Consistency Check

Checked whether:

- `discount_applied`
- `promo_code_used`

were redundant.

`promo_code_used` was subsequently dropped.

### Database Integration

Connected the Python script to **MySQL** and loaded the cleaned DataFrame into the database for SQL-based analysis.

---

## 🗄️ Data Analysis using SQL

Structured analysis was performed in **MySQL** to answer key business questions.

### Business Questions

1. **Revenue by Gender**  
   Compared total revenue generated by male vs. female customers.
   ![](Screenshot2026-09-10105651.png)

3. **High-Spending Discount Users**  
   Identified customers who used discounts but still spent above the average purchase amount.

4. **Top 5 Products by Rating**  
   Found products with the highest average review ratings.

5. **Shipping Type Comparison**  
   Compared average purchase amounts between Standard and Express shipping.

6. **Subscribers vs. Non-Subscribers**  
   Compared average spend and total revenue across subscription status.

7. **Discount-Dependent Products**  
   Identified the 5 products with the highest percentage of discounted purchases.

8. **Customer Segmentation**  
   Classified customers into:
   - New
   - Returning
   - Loyal

   based on purchase history.

9. **Top 3 Products per Category**  
   Listed the most purchased products within each category.

10. **Repeat Buyers & Subscriptions**  
   Checked whether customers with more than 5 purchases are more likely to subscribe.

11. **Revenue by Age Group**  
    Calculated the total revenue contribution of each age group.

---

## 📈 Power BI Dashboard

An interactive **Power BI dashboard** was built to present the insights visually.

The dashboard provides a visual representation of the customer shopping behavior and the results obtained from the analysis.

---

## 💡 Business Recommendations

### 1. Boost Subscriptions

Promote exclusive benefits for subscribers to encourage more customers to subscribe.

### 2. Customer Loyalty Programs

Reward repeat buyers to encourage them to move into the **"Loyal"** customer segment.

### 3. Review Discount Policy

Balance the sales benefits of discounts with appropriate margin control.

### 4. Product Positioning

Highlight top-rated and best-selling products in marketing campaigns.

### 5. Targeted Marketing

Focus marketing efforts on:

- High-revenue age groups
- Customers using express shipping

---

## 🛠️ Tech Stack

- **Python**
- **Pandas**
- **MySQL**
- **SQL**
- **Power BI**

---

## 🔄 Project Workflow

```text
Raw Transactional Data
        ↓
Data Loading with Python
        ↓
Data Exploration & Cleaning
        ↓
Feature Engineering
        ↓
MySQL Database
        ↓
SQL Business Analysis
        ↓
Power BI Dashboard
        ↓
Business Insights & Recommendations
```
