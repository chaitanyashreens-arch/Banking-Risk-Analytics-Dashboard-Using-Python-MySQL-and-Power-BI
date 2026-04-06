# Banking-Risk-Analytics-Dashboard-Using-Python-MySQL-and-Power-BI
Banking Risk Analytics Dashboard Using Python, MySQL and Power BI

1. Overview
This project focuses on building a Banking Dashboard using Power BI to understand risk analytics in the banking and financial services sector. The primary goal is to analyze customer data and support decision-making in loan approvals by evaluating whether an applicant is likely to repay a loan.
The dashboard enables banks to minimize financial risk by leveraging data-driven insights derived from customer profiles, financial behavior, and transaction history.

2. Problem Statement
To develop a basic understanding of risk analytics in banking and understand how data can be used to reduce the risk of financial loss while lending to customers.

3. Solution Approach

The solution involves creating interactive Power BI dashboards that:
•	Analyze customer financial profiles
•	Evaluate loan repayment likelihood
•	Provide insights for informed lending decisions
These dashboards help banks decide whether to approve or reject loan applications based on risk indicators.

4. Dataset Description

The dataset contains multiple interrelated tables representing banking and client information. These tables are connected using primary and foreign keys.
Key Tables:
•	Banking Relationship
•	Client-Banking
•	Gender
•	Investment Advisor
•	Period
The dataset includes details such as:
•	Client demographics
•	Account balances
•	Loan details
•	Deposits and investments

5. Data Cleaning & Transformation

Several calculated columns were created to enhance analysis:
•	Engagement Timeframe
Categorizes customer relationship duration with the bank
•	Engagement Days
Calculates total days since the customer joined the bank
•	Engagement Days = DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)
•	Income Band
Categorizes income levels:
o	Low (< 100,000)
o	Mid (< 300,000)
•	Processing Fees
Derived from Fee Structure:
o	High Fee → 5% processing fee

6. DAX Calculations

SUM
Adds all values in a column
Bank Deposit = SUM('Clients - Banking'[Bank Deposits])
DISTINCTCOUNT
Counts unique values
Total Clients = DISTINCTCOUNT('Clients - Banking'[Client ID])
SUMX
Calculates row-wise expressions and sums them
Total Fees = SUMX('Clients - Banking', [Total Loan] * 'Clients - Banking'[Processing Fees])
SWITCH
Used for conditional logic (similar to IF-ELSE)
DATEDIFF
Calculates difference between dates
Engagement Days = DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)

7. Key Performance Indicators (KPIs)

Customer Metrics
•	Total Clients
Total number of unique customers
Loan Metrics
•	Total Loan
•	Total Loan = [Bank Loan] + [Business Lending] + [Credit Cards Balance]
•	Bank Loan
•	Business Lending
•	Credit Cards Balance
Deposit Metrics
•	Total Deposit
•	Total Deposit = [Bank Deposit] + [Savings Account] + [Foreign Currency Account] + [Checking Accounts]
•	Savings Account
•	Checking Account
•	Foreign Currency Account
Fee Metrics
•	Total Fees
Based on loan and processing charges
Engagement Metrics
•	Engagement Length
Total duration of customer relationship

8. Dashboard Visualizations

1. Home Dashboard
•	Overview of KPIs
•	Quick summary of client and financial data
2. Loan Analysis Dashboard
•	Loan distribution by:
o	Gender
o	Investor type
o	Nationality
•	Risk insights and loan trends
3. Deposit Analysis Dashboard
•	Breakdown of deposits across account types
•	Comparative analysis of investment patterns
4. Summary Dashboard
•	Combined view of loans, deposits, and client insights
•	High-level decision-making metrics

9. Results & Insights

•	Private banks tend to have a higher number of clients
•	Certain nationalities show higher loan amounts
•	Customer segmentation helps identify high-risk borrowers
•	Deposit patterns reveal investment preferences

10. Conclusion
Power BI dashboards provide a powerful way to analyze banking data and support risk management. By visualizing key financial metrics and customer behavior, banks can make informed decisions, reduce default risks, and optimize lending strategies.

11. Future Scope
•	Implement predictive models for loan default risk
•	Integrate real-time banking data
•	Enhance dashboards with AI-driven insights
•	Improve customer segmentation strategies

12. How to Use This Project
•	Load dataset into Power BI
•	Perform data cleaning and transformation
•	Create relationships between tables
•	Build DAX measures and KPIs
•	Design dashboards using visuals
•	Analyze insights for decision-making

End of Report

