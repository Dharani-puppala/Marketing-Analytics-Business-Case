# Marketing-Analytics-Business-Case
PYTHON,SQL(SSMS), EXCEL, POWERBI

# Introduction to Business Problem

ShopEasy, an online retail business, is facing reduced customer engagement and conversion rates despite launching several new online marketing campaigns. They are reaching out to you to help conduct a detailed analysis and identify areas for improvement in their marketing strategies.

## Subject
**Request for Data Analysis to Improve Marketing Strategy**

Despite increased investment in marketing, ShopEasy has observed a decline in customer engagement and conversion rates. Marketing expenses have risen, but the return on investment is falling short of expectations. ShopEasy has collected data from various sources, including customer reviews, social media comments, and campaign performance metrics, to gain insights into the effectiveness of their strategies. By analyzing this data, they aim to uncover customer needs, pain points, and areas for optimization to improve their marketing efforts, customer experience, and overall performance.


## KPI Requirements
1. **Conversion Rate**: Percentage of website visitors who make a purchase.
2. **Customer Engagement Rate**: Level of interaction with marketing content (clicks, likes, comments).
3. **Average Order Value (AOV)**: Average amount spent by a customer per transaction.
4. **Customer Feedback Score**: Average rating from customer reviews.

## Goals
1. **Increase Conversion Rates**:
   - **Goal**: Identify factors impacting the conversion rate and provide recommendations to improve it.
   - **Insight**: Highlight key stages where visitors drop off and suggest improvements to optimize the conversion funnel.
2. **Enhance Customer Engagement**:
   - **Goal**: Determine which types of content drive the highest engagement.
   - **Insight**: Analyze interaction levels with different types of marketing content to inform better content strategies.
3. **Improve Customer Feedback Scores**:
   - **Goal**: Understand common themes in customer reviews and provide actionable insights.
   - **Insight**: Identify recurring positive and negative feedback to guide product and service improvements.
   - 
# STEP 1: Extracting and Cleaning Marketing Data with SQL(SSMS,EXCEL,SQL SERVER EXPRESS,SQL PROFILER,CTE)

## Purpose

This project focuses on preparing marketing data for analysis by applying a series of SQL queries for categorization, enrichment, cleaning, and standardization. The goal is to enhance the quality and usability of the data, enabling better insights and decision-making for marketing strategies.

## Steps and Context

### 1. **Categorizing Products by Price**

Products are divided into three categories based on their price:
- **Low**: Less than $50
- **Medium**: Between $50 and $200
- **High**: Greater than $200

This categorization helps with targeted marketing strategies and segmentation.

### 2. **Enriching Customer Data with Geographic Information**

Using a `LEFT JOIN` between the `Customers` and `Geography` tables to enrich customer profiles with location-based data.

Geographic insights help personalize marketing campaigns and optimize regional strategies.

### 3. **Cleaning Customer Reviews for Sentiment Analysis**

- Removing whitespace issues in reviews using the `REPLACE` function.
- Clean reviews are crucial for accurate sentiment analysis and understanding customer feedback.

### 4. **Normalizing Engagement Data**

Standardizing data fields such as dates, text, and URLs using SQL functions like:
- `UPPER`
- `LEFT`
- `FORMAT`
- `REPLACE`

This ensures consistency and uniformity for accurate reporting and analysis.

### 5. **Identifying and Removing Duplicate Records**

Using a Common Table Expression (CTE) to detect duplicate entries in the `Customer_Journey` table based on:
- `CustomerID`
- `ProductID`
- `VisitDate`
- `Stage`
- `Action`

- Retaining only the first occurrence while handling missing values (e.g., replacing null `Duration` values with the average for the same `VisitDate`).
- Ensures data integrity and removes redundancy.

## Key Benefits

- **Improved data consistency and quality for analysis.**
- **Enhanced ability to identify customer behavior patterns.**
- **A solid foundation for advanced insights and optimized marketing strategies.**
  
## Error1

The error message "Access is denied (Error 5)" indicates that SQL Server does not have the necessary permissions to write the database files to the specified location.

**Solution Steps:**
1. Run SSMS as Administrator
   - Close SQL Server Management Studio (SSMS).
   - Right-click on the SSMS shortcut and choose Run as Administrator.
   - Try restoring the database again.
2. Grant Permissions to SQL Server Service Account
   - Find the SQL Server Service Account:(C:\Windows\SysWOW64\SQLServerManager16.msc)
   - Open SQL Server Configuration Manager.
   - Navigate to SQL Server Services.
   - Locate SQL Server (SQLEXPRESS).
   - Check the Log On As column (commonly NT SERVICE\MSSQL$SQLEXPRESS or NT AUTHORITY\SYSTEM).
   - Grant Full Control to the SQL Server Service Account:
   - Navigate to C:\Program Files\Microsoft SQL Server\MSSQL16.SQLEXPRESS\MSSQL\DATA.
   - Right-click on the folder and choose Properties.
   - Go to the Security tab.
   - Click Edit, then Add.
   - Enter the SQL Server service account (e.g., NT SERVICE\MSSQL$SQLEXPRESS).
   - Grant Full Control permissions and click Apply > OK.

