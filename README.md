
#  ACKO INSURANCE DASHBOARD — Power BI Project


##  Dashboard Preview

![ACKO Insurance Dashboard](https://github.com/Groverbhumi/Acko_Insurance_Dashboard/blob/main/dashboard_1.png?raw=true)

---
![ACKO Insurance Dashboard - Page 2](https://github.com/Groverbhumi/Acko_Insurance_Dashboard/blob/main/dashboard_2.png?raw=true)
---





## 📊 Problem Statement

This dashboard provides a comprehensive view of **ACKO Insurance’s performance**, helping the company track and analyze customer claims, premiums, and coverage data.  
It enables the insurance provider to identify trends in **policy types**, understand **customer demographics** (by age and gender), and monitor the **active/inactive policy ratio**.  
By visualizing key metrics such as claim amounts, premium amounts, and coverage distribution, ACKO can improve decision-making, reduce claim delays, and design better insurance products for its customers.

---

## ⚙️ Steps Followed

 Step 1: The dataset (CSV file) was loaded into **Power BI Desktop**.

 Step 2:  In **Power Query Editor**, under the **View tab** (Data Preview section), the options  **Column distribution**, **Column quality**, and **Column profile** were checked to understand data completeness and consistency.



Step 3:Since profiling by default applies only to the first 1000 rows, **Column profiling based on entire dataset** was selected for accurate data quality insights.

 Step 4:**Removed Duplicates** — Some records were found to be repeated; hence, duplicates were removed to ensure accurate aggregations and avoid double counting of claim amounts or premium amounts.

 Step 5: Three **slicers** were added for interactive filtering:

- PolicyNumber  
- ClaimNumber  
- CustomerID

These allow users to explore data for specific policies, claims, or customers.

 Step 6:  Under the **Insert tab**, a **Text Box** was added with the company name:  
> **ACKO INSURANCE PVT. LTD.**

This provides branding and clarity to the report.

Step 7: Three **Card Visuals** were added to represent KPIs:

| Metric | Value |
|---------|--------|
| Premium Amount | 5.97M |
| Coverage Amount | 600.33M |
| Claim Amount | 16.90M |

 Step 8:
A **Multi-Row Card** was added for **gender distribution**:

| Gender | Count | Premium Amount | Coverage Amount | Claim Amount |
|---------|--------|----------------|------------------|--------------|
| Female | 5000 | 2.99M | 301.60M | 8.41M |
| Male | 5000 | 2.98M | 298.73M | 8.49M |
| **Total** | **10000** | **5.97M** | **600.33M** | **16.90M** |

This shows gender-wise contribution across financial indicators.

 Step 9:
A **Ribbon Chart** was created to show the **Number of Claims by Claim Status**.  
This visual displays how many claims are **Pending**, **Settled**, or **Rejected**.

Step 10:  
A **Bar Chart** was created for **Premium Amount by Policy Type**  
(Travel, Health, Auto, Life, Home), showing which types generate the most revenue.

Step 11:
A **Conditional Column** was created to group customers by **Age Group** using DAX:

```DAX
Age Group =
IF(member[Age] <= 24, "Young Adult",
    IF(member[Age] <= 60, "Adult",
     "Old"))

```
Then, a **Line Chart** was plotted for Claim Amount vs Age Group to see which age segments file higher claims

Step 12 – Creating Active/Inactive Column**
A **Conditional Column** named **Active/Inactive** was created using the following DAX expression:

```DAX
Active/Inactive =
IF(member[PolicyEnd Date] < DATE(2024,12,10), "Inactive", "Active")
```

Step 13 – Donut Chart (Active vs Inactive Users)**
A **Donut Chart** was plotted to show the **Count of Active vs Inactive Users**.

| Status   | Count | Percentage |
|-----------|--------|-------------|
| Active    | 5.81K  | 58.11% |
| Inactive  | 4.19K  | 41.89% |



Step 14 – Table Visual (Policy Type vs Claim Status)
A **Table Visual** was created showing **Policy Type vs Claim Status** to analyze how **claim statuses** vary across different **policy categories**.

Step 15 – **Drill-through functionality** was enabled for the **Policy Type** field, allowing users to:
- Click on a specific policy category (like **Travel** or **Health**)
- Explore deeper insights related to that specific policy type.



 Step 16 – **Role-Based Access Control**
**Roles** were assigned according to **policy types** (Travel, Health, Auto, etc.) for **data security and controlled access**, ensuring that only authorized personnel can view relevant policy data.

---

## 📈 Insights



### **1️⃣ Customer Overview**
| Metric | Value |
|--------|-------|
| Total Members | 10,000 |
| Male | 5,000 |
| Female | 5,000 |

---

### **2️⃣ Financial Overview**
| Metric | Value |
|--------|--------|
| Total Premium Collected | ₹5.97 Million |
| Total Coverage Provided | ₹600.33 Million |
| Total Claim Amount | ₹16.90 Million |

---

### **3️⃣ Gender-Wise Breakdown**
| Gender | Premium Amount | Coverage Amount | Claim Amount |
|---------|----------------|-----------------|---------------|
| Female | ₹2.99M | ₹301.60M | ₹8.41M |
| Male | ₹2.98M | ₹298.73M | ₹8.49M |

💡 **Insight:** Both genders contribute nearly equally to the overall insurance portfolio.

---

### **4️⃣ Claim Status Summary**
| Status | Count |
|--------|--------|
| Rejected | 4.4K |
| Settled | 3.4K |
| Pending | 2.3K |

⚠️ **Observation:**  
Most claims fall under **“Rejected”**, indicating potential areas for **process improvement**.

---

### **5️⃣ Policy Type Analysis**
| Policy Type | Premium Amount |
|--------------|----------------|
| Travel Insurance | ₹2.5M |
| Health Insurance | ₹1.2M |
| Auto Insurance | ₹1.0M |
| Life Insurance | ₹0.7M |
| Home Insurance | ₹0.6M |

🏆 **Insight:**  
**Travel Insurance** generates the **highest premium** among all policy categories.

---

### **6️⃣ Age Group Insights**
| Age Group | Claim Amount |
|------------|---------------|
| Adult | ₹8.8M |
| Elder | ₹6.4M |
| Young Adult | ₹1.7M |

📉 **Insight:**  
**Adults** contribute the **highest claim amount**, followed by **Elder** policyholders.

---

### **7️⃣ Policy Activity**
| Status | Count | Percentage |
|---------|--------|-------------|
| Active | 5.81K | 58.11% |
| Inactive | 4.19K | 41.89% |

📊 **Observation:**  
Over half of all policies are **active**, showing decent retention but room for **renewal improvement**.

---

## 🧠 Conclusion

This **Power BI Dashboard** successfully visualizes the key business metrics for **ACKO Insurance Pvt. Ltd.**

It enables the company to:
- Monitor overall **insurance performance**
- Understand **customer demographics** by gender and age
- Track **claim patterns** and **status distribution**
- Identify **high-performing** and **low-performing** policy types
- Strengthen **data-driven decision-making** for renewals and customer retention

💡 **Final Insight:**  
By leveraging this dashboard, **ACKO Insurance** can **optimize policy offerings**, **improve customer satisfaction**, and **increase profitability** through a data-driven strategy.

---

## 🪪 Copyright & Credits

© 2025 **Bhumika Grover**  
👩‍💻 *Dashboard Designed & Documented by Bhumika Grover*  
  🔗 *All visuals, analysis, and documentation are original work.*

---



