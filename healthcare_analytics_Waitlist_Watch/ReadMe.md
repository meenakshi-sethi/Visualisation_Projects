# 🏥 Healthcare Analytics Dashboard:- "Waitlist Watch"

## 📌 Project Overview
This project demonstrates an **End-to-End Power BI Dashboard Development** process for **Healthcare Analytics**. It covers everything from **data collection** to **visualization**, using real-world data about **Patient Waiting Lists**.

The **dashboard** enables:
- **Tracking** the current status of the patient waiting list.
- **Analyzing** historical trends for **Inpatients & Outpatients**.
- **Performing specialty-level & age profile analysis**.
- **Interacting** with data through filters and drill-through reports.

---
## 🎯Purpose
The Waitlist Watch Dashboard is designed to analyze and monitor patient waitlists in hospitals and healthcare institutions. It serves as a decision-making tool for healthcare administrators by providing real-time insights into patient waiting times, historical trends and specialty-level analysis.

### **💡 Key Objectives:**
✔ **Track Patient Waiting Lists** – Monitor total waiting times across inpatient and outpatient services.  
✔ **Analyze Trends** – Identify **historical patterns** in patient wait times across different months and years.  
✔ **Specialty & Age Profile Insights** – Compare wait times across **different specialties and age groups**.  
✔ **Improve Hospital Efficiency** – Help hospital management **optimize resources and staffing**.  
✔ **Interactive Reporting** – Allow users to filter by **time period, specialty, and case type** for deeper insights.  
✔ **Automated Data Refresh** – Ensure **up-to-date insights** with minimal manual intervention.  

---

## **📌 Who are the Stakeholders?**
This dashboard is designed for **healthcare professionals, administrators, and analysts** who rely on **data-driven insights** for **operational improvements and policy decisions**.

### **📊 How This Dashboard Helps Each Stakeholder**
| Stakeholder               | Key Benefits |
|---------------------------|-------------|
| **Hospital Administrators** | Improve patient flow, resource allocation, and operational efficiency. |
| **Healthcare Data Analysts** | Gain deeper insights into waitlist trends, patterns, and specialty-based performance. |
| **Doctors & Medical Staff** | Understand patient wait times and plan appointments accordingly. |
| **Policy Makers** | Use analytics to drive improvements in public healthcare services. |
| **IT & BI Teams** | Maintain and automate **Power BI dashboards** for real-time reporting. |

---

### **🚀 Why is This Dashboard Important?**
- **Reduces bottlenecks** in hospitals by highlighting long wait times.  
- **Improves decision-making** through **data-driven insights**.  
- **Enhances patient experience** by enabling better scheduling.  
- **Supports automation** by integrating **Power BI refresh mechanisms**.  

---

## 📊 Dashboard Preview
*(Screenshots of the dashboard visuals for quick reference)*

![Summary Page](https://github.com/meenakshi-sethi/Visualisation_Projects/blob/main/healthcare_analytics_Waitlist_Watch/Images/Waitlist_Summary_Page_1.png)

![Detailed Page](./Images/Detailed_Page.png)

![ER Daigram](./Images/Tooltip_Page.png)

---



---
## 📌 End-to-End Power BI Development Process

The development of this dashboard followed **nine key steps**:

### **1️⃣ Requirement Gathering**
**📍 Identify Stakeholders:**  
- Determined primary stakeholders (domain experts, healthcare leaders).
- Established a **point of contact** for insights and feedback.

**📍 Understand Business Objectives:**  
- Through stakeholder meetings, defined **dashboard goals**:
  - Improve **waiting list tracking**.
  - Provide **monthly trends for Inpatients & Outpatients**.
  - Enable **detailed specialty-level analysis**.

**📍 High-Level Data Study:**  
- Explored **data sources**, **column descriptions**, **data types**, and **missing values**.

**📍 Define Scope:**  
- Metrics: **Average & Median Wait Time, Current Total Waitlist**.
- Time Frame: **2018 – 2021**.
- Views: **Summary & Detailed Page for Granular Analysis**.

---

### **2️⃣ Data Collection**
Power BI supports 200+ data connectors; for this project, we used:
- **Excel / CSV**
- **Folder Connection**

🔗 **Dataset Used:** *(Provide a download link if available)*  
[Download Dataset](./Data/Healthcare_Waitlist.csv)

---

### **3️⃣ Data Transformation**
Data cleaning was performed using **Power Query Editor**. Key transformations:
- **Renaming Columns** (e.g., aligning `Specialty_Name` fields across tables).
- **Rearranging Columns** for consistency.
- **Appending Inpatient & Outpatient Data** into a unified dataset (`All_Data`).
- **Replacing & Trimming Values** (e.g., cleaning age group values: `"18+ months"` → `"18 months"`).

---

### **4️⃣ Data Modelling**
To ensure accurate reporting, **data relationships** were established:
- **Hid redundant tables** (`Inpatient`, `Outpatient`).
- **Created specialty mappings** for grouping similar categories.
- **Connected related tables** using **Power BI Model View**.

🛠️ **Steps to Create Relationships:**
1. Import **specialty mapping file**.
2. Link `Specialty_Name` from `All_Data` → `Specialty` in `Mapping_Specialty`.
3. Ensure **one-to-many relationships** are properly configured.

---

### **5️⃣ Visualization Blueprint**
- A wireframe was **sketched & approved** before implementation.
- Key visual elements:
  - **Card visuals** for **KPIs**.
  - **Doughnut & Column charts** for **trend analysis**.
  - **Line charts** for **time-series patterns**.
  - **Slicers & Filters** for **interactive selection**.

---

### **6️⃣ Dashboard Layout & Design**
**🎨 Design Best Practices Used:**
- **Enabled Gridlines & Snap to Grid** for uniform layout.
- Used **consistent colors & spacing**.
- Kept **charts and slicers clearly labeled**.

📌 **Key DAX Measures Used:**
```DAX
Latest Month Wait List = CALCULATE(SUM(All_Data[Total]), All_Data[Archive_Date] = MAX(All_Data[Archive_Date]))

PY Latest Month Wait List = CALCULATE(SUM(All_Data[Total]), All_Data[Archive_Date] = EDATE(MAX(All_Data[Archive_Date]), -12))

Avg/Med Wait List = SWITCH(VALUES('Calculation Method'[Calc Method]),"Average", [Average Wait List], "Median", [Median Wait List])

```
---

### **7️⃣ Adding Interactivity**
Enhancements included:
✅ **Drill-through filters** for deeper insights.  
✅ **Navigation buttons** for a seamless user experience.  
✅ **Tooltips** for providing additional context.  

📌 **Tooltip Page Setup:**
- Created a **new page** in Power BI.
- Added a **bar chart** for `Specialty vs. Total Waitlist`.
- Linked this **Tooltip Page** to visuals.

---

### **8️⃣ Testing & Deployment**
🛠️ **Testing Approach:**
- Verified **data accuracy** across **different filters & date ranges**.

🚀 **Deployment Considerations:**
- Implemented **Row-Level Security (RLS)** for access control.
- Configured **automated Power BI Service Refresh**.

---

### **9️⃣ Routine Refresh & Maintenance**
The dashboard is **designed for long-term use**, with:
- **Monthly Data Refresh** using Power BI’s **Folder Connection**.
- **Scheduled Refresh Setup** to keep reports updated.
- **Ongoing Performance Monitoring**.

---

## 📂 Files in This Repository

📌 **Power BI File (`.pbix`)**  
🔗 [Download Healthcare Dashboard](./PowerBI_Files/Healthcare_Dashboard.pbix)

📌 **Datasets (`CSV / Excel`)**  
📂 [Download Data](./Data/Healthcare_Waitlist.csv)

---

## 📥 How to Use This Dashboard
1️⃣ **Clone This Repository:**
```bash
git clone https://github.com/yourusername/Healthcare_Analytics_Dashboard.git
```
2️⃣ **Open Power BI Desktop**.  
3️⃣ **Load the `.pbix` file** from `/PowerBI_Files/Healthcare_Dashboard.pbix`.  
4️⃣ **Ensure Data Connection** (update paths if necessary).  
5️⃣ **Explore Insights** & interact with filters.

---

## 📢 Contribution & Feedback
- Feel free to **fork & enhance** this project!

---

### 🎉 **Thank You for Exploring This Dashboard!**
---
