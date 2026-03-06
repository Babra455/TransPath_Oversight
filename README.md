# TransPath Oversight
 
**Author:** Odongo Babra 
**Date:** 2025-03-7

--- 
 
## Project Background.

TransPath is a Transaction Reconciliation and System Integrity analysis designed to investigate discrepancies across our payment infrastructure. Following customer complaints, settlement mismatches, and audit concerns, this project examines the full transaction lifecycle across the Mobile App, Banklink, NIBBS, CoralPay, and IRecharge systems.
The objective is to identify missing, duplicated, misrouted, or inconsistent transactions, quantify financial exposure, assess service provider reliability, and pinpoint breakdowns in the payment pipeline. The findings will support executive decision-making, strengthen financial accuracy, and restore operational integrity across our transaction ecosystem.

[Presentation Slides](https://docs.google.com/presentation/d/1YS-3MZQF1xK9ZiC4eMBT_2OKXkTFlUIMe6rlkNwE7Fo/present?slide=id.p)

--- 
 
## Project Objective 
 - Provide actionable, data-driven recommendations to improve transaction integrity, prevent future losses, and strengthen operational controls.
 - Analyze temporal patterns of failures, including peak hours, days of the week, and specific months, to identify potential system capacity or partner issues.
 - Assess the reliability of all service providers by measuring success rates, missing transactions, and status mismatches to inform operational decisions.
 - Quantify the financial impact of missing, failed, or duplicated transactions, including daily average losses and total exposure.
 - Compare transaction statuses across all systems to ensure consistency and prevent accounting errors or customer disputes.
 - Detect duplicate or missing utility payments and verify that each transaction is routed to the correct provider (CoralPay or IRecharge).
 - Identify orphaned transactions in downstream systems and determine where the transaction flow breaks or data integrity is compromised.
 - Reconcile all bank transfers to ensure that every transaction initiated in the app correctly passes through Banklink and NIBBS for final settlement.



--- 
 
## Datasets 

Apps_transactions.csv  -  This dataset contains all customer-initiated transactions with columns including txnRef, Date, Time, transaction_type, amount, status, and provider. It serves as the primary source of truth for both bank transfers and utility payments, enabling tracking, reconciliation, and validation of transaction activity across all payment channels.

Banklink_transactions.csv  -  This dataset includes transactions processed through the Banklink gateway, with columns such as merchantRef, transaction_id, amount, status, Date, and Time. It allows analysis of bank transfer processing, identification of gateway failures, and verification of settlement flow to NIBSS.

Nibbs_transactions.csv  -  This dataset captures final bank settlement records, containing transaction_id, amount, status, and settlement_date. It enables reconciliation with Banklink transactions, verification of successful settlements, and identification of transactions that fail to reach the interbank settlement system.

Coralplay_transactions.csv -  This dataset records utility transactions processed by CoralPay, with columns including txnRef, Date, Time, service_type, amount, and status. It supports tracking and validation of CoralPay-processed payments, detection of duplicates, and assessment of transaction delivery accuracy.

Irrecharge_transactions.csv  -  This dataset contains utility payments handled by IRecharge, with columns such as txnRef, Date, Time, service_type, amount and status. It allows monitoring of IRecharge transactions, validation against App records, identification of routing errors, and detection of missing or duplicate transactions.


--- 
## Key Findings
1.	The hour with the highest number of transaction failures is 13:00, followed by 04:00 and 14:00, while the lowest failures occur at 01:00, 18:00, and 08:00.
2.	 Day 6 records the highest number of failures, followed by Day 4, and Day 2 has the lowest number of failures.
3.	Monthly trends indicate that Month 3 has the highest number of failures, followed by Month 7, whereas Month 2 and Month 9 record the lowest failures.
4.	Status inconsistencies exist across all systems, with the largest mismatches between the app and Banklink, totaling 922, while app–CoralPay mismatches are the lowest at 489.
5.	There are no duplicate utility transactions and no transactions assigned to the wrong provider, indicating that utility transactions are being accurately recorded.
6.	 CoralPay processes a higher number of transactions, including both successful and failed ones, and maintains a high success rate of 81.85%, while NIBSS has the highest number of failed transactions at 7,516, resulting in a failure rate of 20.52%.
7.	Orphaned transactions, which occur when a transaction appears in the system without a corresponding match in partner records, are highest for Banklink at 1,140, with a high total orphaned amount, and lowest for iRecharge at 371 with a lower total amount.
8.	Overall, the total failed transaction amount is 240,524,436.96, with missing amounts in Banklink and NIBSS of 52,653,820.81 and 82,540,011.63 respectively, leading to an average daily loss of 329,485.53 and a total financial exposure of 1,378,399,256.96, highlighting the need for improved monitoring and reconciliation.


--- 
## Recommendations 
1.	Hourly Failures: Implement time-based monitoring and alerts for high-failure hours (13:00, 04:00, 14:00) and consider load balancing or additional system checks during these peak hours to reduce failures.
2.	 Daily Failures: Investigate processes on Day 6 and Day 4 to identify operational or system patterns causing spikes, and establish daily reconciliation routines to catch errors early.
3.	Monthly Failures: Perform monthly trend analysis to understand recurring issues in Months 3 and 7, and schedule preventive system maintenance ahead of high-failure months.
4.	 Status Inconsistencies: Strengthen data reconciliation between the app and Banklink, implement automated mismatch detection, and conduct regular audits to reduce accounting errors and disputes.
5.	 Utility Transactions: Continue strict validation controls to maintain accurate utility transactions, and implement periodic reviews to ensure no duplicate or misassigned transactions occur.
6.	 Provider Performance: Work with NIBSS to improve reliability and reduce failed transactions, while leveraging CoralPay’s high success rate as a benchmark for best practices across providers.
7.	Orphaned Transactions: Implement automated orphan detection and resolution processes, especially for Banklink, to minimize unmatched transactions and improve transaction alignment.
8.	 Financial Exposure: Establish real-time monitoring and alerts for failed and missing transactions, strengthen reconciliation processes, and conduct root-cause analysis to prevent recurring financial losses.


 
--- 
 
## Tools & Techniques 
-	Aggregation and Analysis
-	Sorting, Joining and Filtering
-	Data cleaning and transformation in SQL
-	Derived Metrics 
-	Basic descriptive analytics and KPI design 
 
--- 
 
## Project Files (included) 
-	`Trans_Path SQL Script` —  SQL Query
-	`README.md` — this documentation 
-	`MP_SQL_Project_3` – The problem
 
--- 
 
## How to Run / View 
1.	Open `Trans_path SQL Script ` in SQL (desktop recommended)   
2.	Open the SQL script file in your SQL editor.  
3.	Analysis was done entirely using SQL queries.
4.	View the results in the query output/results panel for each section of the analysis.
5.	For a summary of insights and recommended actions view [Presentation Slides](https://docs.google.com/presentation/d/1YS-3MZQF1xK9ZiC4eMBT_2OKXkTFlUIMe6rlkNwE7Fo/present?slide=id.p)
 
 

 
--- 
 
## Contact 
Babra Odongo
odongobabra5@gmail.com
https://www.linkedin.com/in/babra-odongo-047921268/



