# 🏥 HealthConnect Patient Data Dashboard  

## 📊 Project Overview  
This project explores anonymized patient records from **HealthConnect**, a healthcare solutions company.  
The dashboard was built in **Power BI** to analyze **patient demographics, treatment outcomes, and success rates**, providing actionable insights for healthcare management.  

---

## ✅ Key Features of the Dashboard  
- **Patient Demographics Distribution**  
  - Displays age and gender distributions across different health conditions.  

- **Treatment Success Rates by Diagnosis**  
  - Visualizes outcome performance for each medical condition.  

- **Treatment Outcome Comparison**  
  - Compares **Success, Failure, and Inconclusive** outcomes.  

- **Medical Condition by Gender and Age Group**  
  - Stacked charts highlight demographic breakdowns.  

- **Interactive Slicers**  
  - Navigate insights by **Blood Group** and **Insurance Provider**.  

---

## 🛠️ Data Preparation  
- **Column Standardization**  
  - Corrected and cleaned the `Name` column formatting.  

- **Handling Missing Values**  
  - Addressed missing records with imputation and cleaning to ensure reliable insights.  

- **Derived Columns (DAX)**  
  - `Treatment Outcome`: Categorized from `Test Results`  
    - Normal → **Success**  
    - Abnormal → **Failure**  
    - Inconclusive → **Inconclusive**  
  - `Age Group`: Binned into categories → **0–17, 18–35, 36–55, 56–75, 76+**
 
    - **New Measure (DAX)**  
  ```DAX
  Success Rate =
  DIVIDE(
    COUNTROWS(FILTER('Table', 'Table'[TreatmentOutcome] = "Success")),
    COUNTROWS(FILTER('Table', 'Table'[TreatmentOutcome] IN {"Success","Failure"}))
  )

📈 Insights & Findings

👶 Age 0–17 has the lowest medical condition count, while 👨‍🦳 age 36–55 has the highest.

📉 Success rates vary significantly by diagnosis, highlighting areas where treatment protocols could be reviewed.

⚖️ Gender distribution shows conditions that are more common in either male or female patients.

🎯 Insurance provider and blood group slicers allow deeper segmentation of patient populations.

🚀 Technologies Used

Power BI → Dashboarding & Data Visualization

DAX → Custom measures and calculated columns

Excel / CSV → Raw data preprocessing

