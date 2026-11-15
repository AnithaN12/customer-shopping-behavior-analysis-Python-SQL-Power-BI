# 🛍️ Customer Shopping Behavior Analysis

## 📌 Project Overview
This end-to-end data analytics project analyzes **3,900 customer transactions** to uncover purchasing patterns, product preferences, discount sensitivity, and subscription behavior. Using **Python**, **MySQL**, and **Power BI**, the analysis transforms raw transactional records into actionable business recommendations to boost customer retention and revenue.

---

## 📊 Dataset Summary
* **Total Records:** 3,900 rows
* **Total Features:** 18 columns
* **Data Categories:**
  * **Customer Demographics:** Age, Gender, Location, Subscription Status
  * **Purchase Details:** Item Purchased, Category, Purchase Amount (USD), Season, Size, Color
  * **Shopping Behavior:** Discount Applied, Promo Code Used, Previous Purchases, Frequency of Purchases, Review Rating, Shipping Type
* **Data Quality Note:** Identified 37 missing values in the `Review Rating` column.

---

## 🛠️ Tools & Technologies
* **Python (Pandas, SQLAlchemy / PyMySQL):** Data cleaning, exploratory data analysis (EDA), feature engineering, and database ingestion.
* **MySQL:** Structured querying to answer 10 core business questions.
* **Power BI:** Interactive dashboarding and visual storytelling.

---

## 🧹 Data Preparation & Engineering (Python)
1. **Exploratory Inspection:** Checked data types, summary statistics, and distributions using `df.info()` and `df.describe(include='all')`.
2. **Missing Value Imputation:** Filled the 37 missing `Review Rating` entries using the **median rating of each respective product category**.
3. **Standardization:** Converted all column names to `snake_case` for SQL compatibility and readability.
4. **Feature Engineering:**
   * Created `age_group` by binning customer ages into `Young Adult`, `Middle-aged`, `Adult`, and `Senior`.
   * Created `purchase_frequency_days` from purchase frequency records.
5. **Redundancy Removal:** Verified that `discount_applied` and `promo_code_used` contained identical information and dropped `promo_code_used`.
6. **Database Integration:** Loaded the cleaned DataFrame directly into a **MySQL** database for analytical querying.

---

## 🔍 Key SQL Analysis & Findings
Ten structured SQL queries were executed in MySQL to evaluate revenue drivers and customer behavior:

1. **Revenue by Gender:** Male customers generated **\$157,890** in total revenue compared to **\$75,191** from female customers.
2. **High-Spending Discount Users:** Identified discount users whose transaction value still exceeded the overall average purchase amount (**\$59.76**).
3. **Top 5 Highest-Rated Products:** Gloves (**3.86**), Sandals (**3.84**), Boots (**3.82**), Hat (**3.80**), and Handbag (**3.78**).
4. **Shipping Type Comparison:** Express shipping orders averaged **\$60.48**, outperforming Standard shipping at **\$58.46**.
5. **Subscribers vs. Non-Subscribers:** Non-subscribers make up **73%** of customers (2,847 users; **\$170,436** revenue; **\$59.87** avg spend), while subscribers account for **27%** (1,053 users; **\$62,645** revenue; **\$59.49** avg spend).
6. **Most Discount-Dependent Products:** Hat (**50.00%**), Sneakers (**49.66%**), Coat (**49.07%**), Sweater (**48.17%**), and Pants (**47.37%**) had the highest share of discounted sales.
7. **Customer Segmentation:** Segmented the customer base into **3,116 Loyal**, **701 Returning**, and **83 New** customers based on purchase history.
8. **Top 3 Products per Category:**
   * *Accessories:* Jewelry (171), Sunglasses (161), Belt (161)
   * *Clothing:* Blouse (171), Pants (171), Shirt (169)
   * *Footwear:* Sandals (160), Shoes (150), Sneakers (145)
   * *Outerwear:* Jacket (163), Coat (161)
9. **Repeat Buyers & Subscriptions:** Among repeat buyers (>5 purchases), **72.44%** (2,518) are non-subscribers vs. **27.56%** (958) subscribers, highlighting a major conversion opportunity.
10. **Revenue by Age Group:** Young Adults led revenue at **\$62,143 (26.66%)**, followed by Middle-aged at **\$59,197 (25.40%)**, Adults at **\$55,978 (24.02%)**, and Seniors at **\$55,763 (23.92%)**.

---

## 📈 Power BI Dashboard
An interactive Power BI dashboard was built featuring KPI cards (**3.9K Customers**, **\$59.76 Average Purchase Amount**, **3.75 Average Review Rating**), dynamic slicers (Subscription Status, Gender, Category, Shipping Type), and breakdowns of revenue and sales across categories and age groups.

![Customer Shopping Behavior Dashboard](images/dashboard_preview.png)

---

## 💡 Business Recommendations
* **Boost Subscriptions:** Promote exclusive member perks to convert the **72.44%** of non-subscribed repeat buyers into subscribers.
* **Strengthen Loyalty Programs:** Introduce tiered rewards to retain repeat buyers and expand the **Loyal** customer segment.
* **Optimize Discount Strategy:** Audit heavily discounted items (such as Hats and Sneakers at ~50% discount rates) to protect profit margins while sustaining volume.
* **Strategic Product Positioning:** Feature top-rated products (Gloves, Sandals, Boots) and category best-sellers prominently in marketing campaigns.
* **Targeted Marketing:** Prioritize campaigns toward high-revenue **Young Adult** and **Middle-aged** segments as well as **Express Shipping** shoppers.

---


5. Open `powerbi/customer_shopping_dashboard.pbix` in Power BI Desktop to interact with the visuals.

