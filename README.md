
# Insurance Dashboard


### Dashboard Link
[View Power BI Dashboard](https://app.powerbi.com/groups/c67e0fd4-5d3e-473d-8da7-57eb210efe02/reports/c6d24044-e6b9-4879-af3a-9ee300cae635/52253fa598e3e44405e9?experience=power-bi)

### Dashboard Overview 

This Power BI dashboard provides a comprehensive analysis of insurance policies, customers, premiums, coverage, and claims.
It helps stakeholders understand business performance, customer demographics, policy utilization, and claim behavior.

### Dashboard Pages

- **Insurance Overview** - Shows a high-level view of premiums, coverage, claims, and policy distribution.

- **Insurance Data Explorer** - Provides detailed policy and customer-level insights with drill-down analysis.

- **Customer Feedback & sentiment Analysis** - Displays customer feedback and sentiment to evaluate service quality.

## Problem Statement

This dashboard helps insurance companies and stakeholders understand policy performance, customer behavior, and claim patterns. It enables decision-makers to identify high-risk policies, analyze claim trends, and understand which factors most influence insurance outcomes.

By analyzing policy details, customer demographics, coverage information, claims, and customer feedback, this dashboard supports:

* Improved policy performance tracking

* Deeper understanding of customer behavior

* Identification of claim trends and risk patterns

* Informed business and operational decision-making

* Centralized, interactive, and insightful reporting


The dashboard highlights key business indicators such as policy type, premium amount, coverage amount, claim status, customer age group, gender distribution, and customer feedback sentiment.

---
## Steps Followed

# First Report Page: Insurance Overview 

### Step 1: Downloading & Installing Microsoft SQL Server
**Purpose**
To store insurance data in a centralized relational database..

**Steps:**

* Download Microsoft SQL Server Developer Edition

*  Install Database Engine Services

*  Install SQL Server Management Studio (SSMS)

* Verify SQL Server services are running

✅ **Status:** SUCCESS

---

### Step 2: Importing Data to SQL Server

* Open SSMS and connect using Windows Authentication.

*  Create a new database named **InsuranceDB**.
*  Refresh Object Explorer to see the database.

* Import CSV using Import Flat File → Table name: **InsuranceData**.

5. Verify data with:

```
  SELECT * FROM InsuranceData
```

Status: ✅ SUCCESS

---

### Step 3: Connect SQL Server to Power BI Desktop

* Open Power BI Desktop.

* Click Get Data →** SQL Server**.
* Enter Server Name and Database Name **(InsuranceDB)**.

* Choose Import mode.

* Select **InsuranceData** table.

* Open Transform Data to preview dataset.

* Review columns (Policy Number, Customer ID, Gender, Age, Policy Type,Premium Amount,Claim Amount,Claim Status,Claim Date).

* Click Close & Apply to load data.



---

### Step 4: Table View & Data Profiling

* Switch to Table View → review all columns and 10,000 rows.

* Open Power Query Editor → enable Column Quality, Distribution, Profile.

* Analyze Claim Date column:

        • Valid → 56%

        • Empty → 44%

*  Verify data types for each column.

* Understand value distributions (e.g., Gender, Policy Type, Claim Status).




---

### Step 5: Adding Slicers & Text

**Steps:**

* Apply report theme (Dark theme).

* Add slicers: Policy Number, Claim Number, Customer ID.

* Format slicers → dropdown style.

* Add company name in Text Box → Prism Insurance Pvt. Ltd.

* Position and format text for branding.

![Card Visuals](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/Card%20Visuals.png?raw=true)



---

### Step 6: Adding Card Visuals

* Format existing slicers.

* Add Premium Amount Card → Sum aggregation.

* Add Coverage Amount Card.

* Add Claim Amount Card.

* Test interactivity with slicers.

![Coverage Amount](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/Coverage%20Amount.png?raw=true)


![Premium Amount](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/premium%20amount.png?raw=true)


![Claim Amount](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/claim%20amount.png?raw=true)




---

### Step 7: Adding a Multi-Row Card & a Ribbon Chart

* Add Multi-Row Card → display Male/Female counts.

* Format Multi-Row Card → turn off category labels, adjust font & border.

* Enable Multi-Row Card as a filter.

* Add Ribbon Chart → Claim Status vs Count.

* Format Ribbon Chart → data labels, title, color.

![Count of Female and Male](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/COUNT%20OF%20FEMALE%20AND%20MALE.png?raw=true)

**Purpose:**

* Understand customer gender distribution

* Support demographic analysis
---

### Step 8: Adding a Bar Chart & a Line Chart

* Add Stacked Bar Chart → Premium Amount by Policy Type.

* Format Bar Chart → axis, data labels, colors.

* Create Age Group column in Power Query → Young Adult, Adult, Elder.

* Add Line Chart → Claim Amount by Age Group.

* Format Line Chart → markers, shaded area, data labels.

**Purpose:**

* Identify high-value policy types

* Analyze claim behavior across age groups

![Age Group If Condition](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/AGE%20GROUP%20IF%20CONDITION.png?raw=true)

![Age Group](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/AGE%20GROUP.png?raw=true)

---

### Step 9: Adding a Donut Chart & Matrix Visual

* Create Active/Inactive column using Policy End Date.

* Add Donut Chart → Active vs Inactive policies.

* Format Donut Chart → colors, title, labels.

* Add Matrix Visual → Coverage Amount by Policy Type & Claim Status.

* Format Matrix → headers, gridlines, borders.

**Purpose:**

* Monitor policy lifecycle

* Track coverage exposure

![If Active or Inactive](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/IF%20ACTIVE%20OR%20INACTIVE.png?raw=true)

![Active or Inactive New Column](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/ACTIVE%20OR%20INACTIVE%20NEW%20COLUMN.png?raw=true)


---

### Step 10: Publishing the Report to Power BI Service

* Publish report from Power BI Desktop → My Workspace.

* PVerify slicers and visuals online.

* PCreate workspace → Test Power BI Project.

* PRe-publish report → Test Power BI Project workspace.

* Share report with colleagues.


![Publishing to Power BI](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/PUBLISHING%20TO%20POWER%20BI.png?raw=true)

![Power BI Service](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/POWER%20BI%20SERVICE.png?raw=true)


---


### Step 11: Scheduling Refresh in Power BI Service


* Sign in → Test Power BI Project workspace.

* Install On-Premises Data Gateway (Personal Mode).

* Set gateway online and ready.

* Edit data source credentials → Windows authentication.

* Enable Scheduled Refresh → Daily, Time Zone: UTC+5:30.

* Verify refresh updates Premium, Claim, Gender counts.

**Purpose:**

* Ensure up-to-date data availability
---
# Second Report Page: Insurance Data Explorer(Table Visual)

### Step 12: Drill Through Filter

* reate Page 2 → Table Visual.

* Add detailed columns → Policy Number, Customer ID, Claim Number, Age, Gender, Coverage Amount, Premium, Claim Date, Age Group, Active/Inactive.

* Add Drill Through field → Policy Type.

* Test Drill Through from Page 1.

* Validate Back button functionality.

**Purpose:**

* Detailed record-level analysis

![2nd Report Page](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/2nd%20report%20page.png?raw=true)

---

### Step 13: Test Scheduled Refresh & Republishing

* Open report in Power BI Service → confirm refreshed data.

* Check refresh history → succeeded.

* Update Desktop → add Drill Through page → Publish → Replace existing report.

* Validate updated report in Service.

---

### Step 14: Creating & Testing Roles (RLS – Row-Level Security)


* Open Modeling → Manage Roles in Power BI Desktop.

* Create roles based on data filters, e.g.:

      Travel Role → Policy Type = "Travel"

      Health Role → Policy Type = "Health"

* Use View As Role feature to test each role and ensure only relevant rows are visible.

* Save the report with roles defined before publishing.



---

### Step 15: Testing & Implementing RLS in Power BI Service


* After publishing the report with roles defined:

* Go to the Power BI workspace → Datasets → Security.

* Assign users or groups to the appropriate roles (e.g., Travel Role → travel team).

* Ensure On-Premises Data Gateway is running if using SQL Server.

* Test report online using assigned users to verify row-level restrictions are applied correctly.

![Test as Travel Role](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/test%20as%20travel%20role.png?raw=true)

![Test as Health Role](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/Test%20as%20Health%20Role.png?raw=true)


---

### Step 16: Power BI Reports & Dashboards

* Understand Reports vs Dashboards.

* Pin visuals from multiple pages → Dashboard named Insurance.

* Arrange tiles and resize for meaningful layout.

* Share dashboard with colleagues.

![Dashboard](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/Dashboard.png?raw=true)


**Purpose:**

* Single-page executive view

---

# Third Report Page: Customer Feedback & Sentiment Analysis

### Step 17: Sentiment Analysis in Power Query

* Loaded Insurance Customer Feedback.xlsx into Power BI.

* Opened Power Query Editor and ensured the first row was set as headers.

* Applied Sentiment Analysis on the Feedback column to generate a Sentiment Score (0–1).

* Changed the Sentiment Score data type to Decimal Number.

* Created a Conditional Column named **Good/Improvements** to classify feedback:

        ≥ 0.8 → Excellent

        ≥ 0.6 → Good

        Else → Needs Improvement

* Closed and applied the changes to load updated data.

**Purpose**

* To analyze and quantify customer feedback using sentiment scoring.

**Outcome**

* Text-based feedback converted into numeric sentiment values.

* Feedback grouped into meaningful performance categories.

* Enhanced clarity for customer satisfaction evaluation.

### Step 18: Customer Feedback Report in Power BI

* Added a Table visual showing Feedback, Sentiment Score, and Feedback Category.

* Added a Card visual to display the total feedback count.

* Created a Pie/Donut chart to show feedback quality distribution.

* Added a Slicer to filter feedback by category.

* Used interactive visuals to compare positive and improvement-required feedback.

**Purpose**

* To visualize and interpret customer feedback sentiment effectively.

**Outcome**

* Easy identification of customer satisfaction levels.

* Faster insight into areas needing improvement.

* Interactive reporting for better business decisions.

![Sentiment Analysis](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/Sentiment%20Analaysis.png?raw=true)
 

# 📊 Report Snapshots (Power BI Desktop)

## Report 1:  Insurance Overview

![1st Report Page](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/1st%20report%20page.png?raw=true)





## Report 2: Insurance Data Explorer(Table Visual)

![2nd Report Page](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/2nd%20report%20page.png?raw=true)




## Report 3: Customer Feedback & Sentiment Analysis

![3rd Report Page](https://github.com/vinaysaivutukuri/Insurance/blob/main/Images/3rd%20report%20page.png?raw=true)



---


# 📊 Insights

### [1] Insurance Dataset Summary

* A comprehensive insurance dataset was analyzed, covering policies, customers, premiums, coverage amounts, and claims.

* The dataset includes:

        Active and inactive policies

        Claimed and non-claimed policies

* This enables unbiased comparison of risk exposure and claim behavior across multiple dimensions.

➡️ Provides a strong foundation for insurance performance and risk evaluation.

### [2] Policy Type – Primary Business Driver

* Certain policy types (e.g., Health, Travel, Life, Vehicle) contribute:

        Higher premium collections

        Larger coverage exposure

* High-value policy types show:

        Higher average premium amounts

        Greater claim sensitivity

➡️ Policy Type is the most influential factor impacting premium revenue and claim exposure.

### [3] Premium & Coverage Risk Analysis

* Policies with higher coverage amounts generally carry:

        Higher premium values

        Increased claim exposure

* Lower premium policies contribute:

        Lower coverage risk

        Reduced claim impact

➡️ Combining Premium Amount + Coverage Amount improves **risk segmentation** and **underwriting decisions**.

### [4] Age Group & Customer Demographics Analysis

**Adult and Middle Age customer** segments dominate:

* Policy count

        Total premium contribution

* Claim behavior varies across age groups:

        Certain age groups show higher average claim amounts

➡️ Age-based analysis highlights customer **concentration risk and claim tendencies**.

### [5] Gender-Based Distribution Insights

* Gender-wise analysis reveals:

        Balanced participation across male and female customers

        Minor variations in premium contribution and claim frequency

* Gender slicers enable:

        Quick demographic filtering

        Targeted customer analysis

➡️ Gender insights support demographic-driven insurance strategy.

### [6] Claim Status & Policy Lifecycle Analysis

* Claim Status analysis shows:

        Clear separation between claimed and non-claimed policies

        Claim volume varies significantly by policy type

* Active vs Inactive policy analysis highlights:

        Current business exposure

        Policy churn and lifecycle trends

➡️ Claim and policy lifecycle monitoring supports **early risk identification**.

### [7] Time-Based Claim & Policy Trends

* Claim Date analysis reveals:

        Fluctuations in claim volume over time

        Seasonal or period-based claim patterns

* Time-based visuals help:

        Track emerging risk trends

        Monitor operational performance

➡️ Time intelligence enables proactive **claim management** and **trend monitoring.**

### [8] Customer Feedback & Sentiment Analysis

* Customer feedback was analyzed using Sentiment Analysis (0–1 score).

* Feedback classified into:

        Excellent

        Good

        Needs Improvement

* Insights reveal:

        Overall customer satisfaction level

        Clear identification of service improvement areas

➡️ Sentiment analysis enhances service **quality evaluation** and **customer experience strategy**.

### [9] Drill-Through & Explainability Features

* Drill-through functionality enables:

        Record-level policy analysis

        Faster investigation of high-risk or high-value policies


➡️ Supports data-driven, explainable insurance decision-making.
