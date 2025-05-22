RFM Rule-Based Segmentation Report

📊 Project Overview

This project demonstrates the use of RFM (Recency, Frequency, Monetary) analysis for customer segmentation through a rule-based approach. The entire process was implemented in Excel, utilizing built-in functions, pivot tables, and manual scoring techniques. The aim is to identify patterns in customer behavior and strategically segment the customer base for actionable marketing.

📓 Process Summary

Step 1: Data Cleaning & Structuring

Sorted Customer IDs in ascending order to detect and align patterns.

Created essential columns:

Revenue: Total spend per transaction.

Day Difference (DayDiff): Represents tenure/recency based on days between visits.

Frequency: Number of purchases made by a customer.

Used Remove Duplicates to clean repeated invoice records.

Applied PivotTables to aggregate:

Revenue per Customer

Count of unique Invoice Numbers (Frequency)




Step 2: Frequency & Revenue Calculation

Frequency: Count of unique invoices using PivotTable.

Revenue: Sum of spending for each customer.



Step 3: Basket Size Calculation

Formula:

Basket Size = Total Revenue (Monetary) / Frequency

Indicates the average spend per shopping visit.



Step 4: Visit Interval Calculation

Formula:

(Last Visit Date - First Visit Date) / (Frequency - 1)

Used to measure how often the customer visits (e.g., every 52 days).



Step 5: RFM Scoring & Categorization

Manually binned Recency and Frequency scores into 5 equal groups (quintiles).

Assigned R and F scores (1 = worst, 5 = best).

Concatenated scores into a composite segment ID (e.g., F4R2).




Step 6: Segment Labeling

Using R-F score combinations, segments were defined as:

Champions: High F, Low R (recent and frequent buyers)

Loyal Customers: Mid F, Mid R (consistent but not very recent)

Hibernating: Low F, High R (long gone or churned customers)




📂 Excel File Operations Summary

File Used: Copy of Miuul_Retail_RFM_HamV01.xlsx

Key operations performed in the Excel file:

Data Preparation

Filtered blank records and computed TotalPrice using:

= Quantity * Price

Revenue Calculation

Used PivotTable to sum TotalPrice per Customer ID.

Frequency Calculation

Counted unique Invoice values per Customer ID.

Recency Calculation

Used MAX(InvoiceDate) to compute difference:

= MAX(InvoiceDate) - InvoiceDate

Visit Interval

Formula:

= (LastDate - FirstDate) / (Frequency - 1)

Basket Size

Formula:

= Monetary / Frequency

RFM Scoring

Recency and Frequency values divided into 5 bins manually.

Scores assigned based on ranking (e.g., 1 to 5).

Segment Analysis

Segments visualized using PivotTables.

Count and percentage per segment calculated.

🔄 Frequency Examples & Basket Size Explained

🔄 1. Customer-Based Frequency (RFM's "F")

Definition: Total number of purchases made by a customer.

Example:

Customer ID

Invoice No

101

A0001

101

A0002

102

A0003

101

A0004

Customer 101 → 3 purchases → Frequency = 3

Customer 102 → 1 purchase → Frequency = 1

Excel Formula:

=COUNTIF(A:A, A2)

🍎 2. Product-Based Frequency (Market Basket Analysis)

Definition: How many different baskets contain a specific product.

Example:

Basket ID

Product

B001

Apple

B001

Banana

B002

Apple

B003

Banana

B003

Apple

Apple appears in 3 different baskets → Frequency = 3

Banana appears in 2 different baskets → Frequency = 2

Excel Formula (advanced):

=SUM(--(FREQUENCY(IF(B2:B100="Apple", MATCH(A2:A100,A2:A100,0)), ROW(A2:A100)-ROW(A2)+1)>0))

Or use a PivotTable with:

Rows: Product

Values: Distinct Count of Basket ID

🔹 Basket Size

Definition: Average amount spent per transaction by a customer.

Formula:

Basket Size = Monetary / Frequency

Example:

Customer ID

Total Spend

Frequency

101

1500 TL

3

102

900 TL

2

Customer 101 → Basket Size = 1500 / 3 = 500 TL

Customer 102 → Basket Size = 900 / 2 = 450 TL

⏱️ Visit Interval (How Often Customers Shop)

Definition: Average days between a customer's purchases.

Example Data:

Customer ID

Invoice Date

101

01.01.2024

101

05.01.2024

101

10.01.2024

101

20.01.2024

Step 1: Subtract dates

=B3 - B2

Step 2: Calculate average

=AVERAGE(C2:C4)

Alternative formula:

=(LastDate - FirstDate) / (Frequency - 1)

Example: (20 - 1) / (4 - 1) = 19 / 3 = 6.33 days

Insights:

Helps measure loyalty or churn

Useful for campaign timing

Identifies dormant customers
![27](https://github.com/user-attachments/assets/fafd52ee-872f-46c2-9dbd-534fd2825928)
![26](https://github.com/user-attachments/assets/49fb886d-5751-43c4-a3af-7f1437dc81c3)
![25](https://github.com/user-attachments/assets/b692722d-377a-4733-a7be-8dd4182dbfb7)
![24](https://github.com/user-attachments/assets/a199d0b2-391c-4b78-8432-d8a79d874767)
![23](https://github.com/user-attachments/assets/2d34535e-c07d-4f1d-a13f-b31b558cbab1)
![22](https://github.com/user-attachments/assets/5b15a788-370b-40c1-98bb-266e753aa493)
![21](https://github.com/user-attachments/assets/d42283fd-3f75-4fb4-91c7-8a98e08d7869)
![20](https://github.com/user-attachments/assets/d64b5a9d-1578-4c5c-a259-6df4a7bc1085)
![19](https://github.com/user-attachments/assets/0d3a05ee-71d2-4756-8fd2-921f41ea6654)
![18](https://github.com/user-attachments/assets/6fdc4f2c-db54-4eaf-933d-098b7916b1c8)
![17](https://github.com/user-attachments/assets/a0b4e20f-d7af-4318-adec-4d04ab467c69)
![16](https://github.com/user-attachments/assets/1a431b66-ff4f-4bd7-9582-ab451b570087)
![14](https://github.com/user-attachments/assets/3f72e689-7f7f-4323-a62b-07deee4bedf3)
![13](https://github.com/user-attachments/assets/fd6efc4e-a764-460f-8957-5f31cde0ff75)
![12](https://github.com/user-attachments/assets/3c9199b1-eb89-499b-b454-399c10c7adbb)
![11](https://github.com/user-attachments/assets/540daa1b-4123-4083-9f9d-61cc1dc75ab8)
![10](https://github.com/user-attachments/assets/cc489926-2f23-40fc-8dff-1f41605c1110)
![8](https://github.com/user-attachments/assets/40e4e704-f1b1-4d52-b91d-8e6086a17e9d)
![7](https://github.com/user-attachments/assets/f1615636-fc88-40d8-8464-dcdb969d978f)
![6](https://github.com/user-attachments/assets/89af1b3b-7c14-4948-ad71-4bd416e557f7)
![5](https://github.com/user-attachments/assets/7eaf0abe-6853-4b0c-abbb-1044fd18fd55)
![4](https://github.com/user-attachments/assets/7503d420-9ec9-4be2-be41-070cf411278c)
![3](https://github.com/user-attachments/assets/30f32bc8-3c22-4cac-a450-351f71ace1fd)
![2](https://github.com/user-attachments/assets/ab1c0df2-5bf2-45ea-aa98-66c889c52030)
![1](https://github.com/user-attachments/assets/9eb0973c-24c6-42d4-b0a7-a478e850464f)
![image](https://github.com/user-attachments/assets/f2c98af9-2862-4867-920f-8b593cb8e8a3)
![37](https://github.com/user-attachments/assets/012f36d1-8d74-4406-bccb-6df63bc0370b)
![35](https://github.com/user-attachments/assets/b21a4b67-f22d-42e7-99a8-029ba6921df4)
![34](https://github.com/user-attachments/assets/a4f0b5c4-c676-438b-8eb2-ba3405a804b4)
![33](https://github.com/user-attachments/assets/06dc5437-e994-4385-bd7d-d094b9e79060)
![32](https://github.com/user-attachments/assets/cb930e0e-1317-4a28-9a3b-ce3f21c93bde)
![31](https://github.com/user-attachments/assets/6303b2c1-5cc0-4ca9-9af5-b3de57a86818)
![30](https://github.com/user-attachments/assets/db3826f6-b757-40ab-9f3f-f39c80737128)
![29](https://github.com/user-attachments/assets/a8b0e178-448a-4955-b3fa-a6890fae59f6)
![28](https://github.com/user-attachments/assets/96320971-a851-4300-816c-b6dedce97191)

