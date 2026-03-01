# 🏦 Bank Loan Portfolio Analysis (Power BI Dashboard)

---

## 📌 Project Overview

**Tool Used:** Power BI (DAX, Power Query)  
**Dataset:** 38,576 loan records | 24 fields  
**Domain:** Banking & Financial Services  

This project presents a comprehensive analysis of a bank's loan portfolio using Power BI. The goal was to build an interactive, multi-page dashboard that gives the bank a consolidated view of its lending operations, tracking loan performance, identifying risky segments and enabling data-driven decisions around credit risk management.

---

## 🎯 Problem Statement & Objectives

The bank needed a centralized reporting solution to monitor the health of its loan portfolio across thousands of records. Key business questions this analysis answers:

- What percentage of loans are performing (Good) vs defaulting (Bad)?
- How do lending volumes and funded amounts trend month over month?
- Which states, loan purposes and borrower profiles carry the highest risk?
- How do metrics like interest rate and DTI vary across loan grades?

---

## 📊 Dashboard Preview

### Summary Dashboard
![Summary Dashboard](dashboard%20summary.png)


### Overview Dashboard
![Overview Dashboard](dashboard%20overview.png)

### Details Dashboard
![Details Dashboard](dashboard%20details.png)

---

## 📁 Repository Structure

| File | Description |
|---|---|
| `Bank_Loans_Dashboard.pbix` | Power BI dashboard file |
| `Dataset.csv` | Raw dataset (38,576 records) |
| `Bank_Loan_Report.xlsx` | Excel report with KPI breakdown |
| `Bank_Loan_Report_Analysis.pdf` | Written analysis report with insights |
| `Bank_Loan_Terminology.pdf` | Data field definitions and terminology |
| `Bank_Loan_DomainKnowledge.pdf` | Banking domain knowledge reference |
| `dashboard_summary.png` | Summary dashboard screenshot |
| `dashboard_overview.png` | Overview dashboard screenshot |
| `dashboard_details.png` | Details dashboard screenshot |
| `README.md` | Project documentation |

---

## 🔢 Key Metrics

| Metric | Value |
|---|---|
| Total Loan Applications | 38,576 |
| Total Funded Amount | $435.7 Million |
| Total Amount Received | $473.1 Million |
| Average Interest Rate | 12.05% |
| Average DTI Ratio | 13.33% |
| Good Loans (Fully Paid + Current) | 86.2% |
| Bad Loans (Charged Off) | 13.8% |
| Top Lending State | California (6,894 loans) |
| Top Loan Purpose | Debt Consolidation (47.2%) |

---

## 🛠️ Technical Workflow

### 1. Data Cleaning (Power Query)
- Converted date columns to proper Date format
- Removed inconsistent and null records
- Standardized categorical fields like loan status, grade and purpose
- Built a custom **Date Table** using DAX `CALENDAR()` function for time intelligence

### 2. Data Modelling
- Established relationships between fact table and date dimension table
- Marked Date Table as official date table in the model
- Clean star schema for efficient DAX calculations

### 3. DAX Measures Built
- `Total Loan Applications` → `COUNT(loan_id)`
- `Total Funded Amount` → `SUM(loan_amount)`
- `Total Amount Received` → `SUM(total_payment)`
- `Average Interest Rate` → `AVERAGE(int_rate)`
- `Average DTI` → `AVERAGE(dti)`
- `MTD Metrics` → `TOTALMTD()` time intelligence function
- `MoM Metrics` → `CALCULATE()` with `DATEADD()` for previous month comparison
- `Good Loan %` → `CALCULATE(COUNT(id), loan_status IN {"Fully Paid","Current"}) / COUNT(id)`
- `Bad Loan %` → `CALCULATE(COUNT(id), loan_status = "Charged Off") / COUNT(id)`

---

## 📈 Dashboard Structure

### Dashboard 1 (Summary)
KPI cards for Total Applications, Funded Amount, Amount Received, Avg Interest Rate, Avg DTI with MTD and MoM tracking. Good Loan vs Bad Loan breakdown. Loan Status Grid View.

### Dashboard 2 (Overview)
Monthly trend line chart, US State filled map, Loan term donut chart, Employment length bar chart, Loan purpose bar chart, Home ownership tree map

### Dashboard 3 (Details)
Full drill-down grid table with all loan records for individual loan level investigation.

---

## 💡 Key Insights

- **Portfolio is healthy** - 86.2% good loans. Grade D–G loans carry the highest default risk and need tighter monitoring.
- **Debt consolidation dominates** at 47.2% of all applications, opportunity to develop specialized products for this segment.
- **California accounts for 17.9%** of all loans, geographic concentration risk worth monitoring.
- **Loan volumes peak in December** - operational capacity should be planned accordingly for Q4.
- **Total received ($473M) exceeds total funded ($435M)** - the $38M difference represents interest income earned by the bank.

---

## ⚙️ How to View the Dashboard

1. Download `Bank_Loans_Dashboard.pbix`
2. Open in **Power BI Desktop** (free download from Microsoft)
3. Use the slicers on each page to filter by grade, purpose, state and term
4. Explore MTD and MoM metrics on the Summary page

---

## 🧰 Tools & Technologies

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Microsoft%20Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=for-the-badge&logo=microsoft&logoColor=white)

---

 ## 👩‍💻Author
 * Name: Anushka Singh
 * Institution: Gokhale Institute of Politics and Economics
 * Github: https://github.com/09AnushkaSingh
 * Linkedin: https://www.linkedin.com/in/anushka09singh/
 

---





