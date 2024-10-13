## Please click on "Bài thuyết trình Tailwind Trader Project.pdf" to see more details and insights from charts and reports that I created!
## Introduction
### At this project, you helped Tailwind Traders to:
Prepare its sales data and configure its data sources.<br>
Design and develop a data model.<br>
Create a sale report and profit report.
### 1. Prepare sales data and configure data sources
In this stage, I helped Tailwind Traders calculate its Sales data. In Column **W**, I calculated **Gross Revenue** records by multiple **Product Gross Price** and **Quantity Purchased** column and in **Column X** calculated the **Total Tax** records 
![image](https://github.com/user-attachments/assets/318336d2-456e-4fdc-996f-85a783a8f14d)

Then, I helped Tailwind Traders configure its data sources.<br>
Firstly, Load 3 excel files to PowerBI and chosen **Transform**. Within **Power Query**, In **Sales** table find the **OrderID** column, set the data type to Whole Number and set data type properly in other columns
In the **View tab**, upon selecting the **Column Quality**, **Column Distribution**, and **Column Profile** to check data quality, identify errors, missing values...and ensure the Valid percentage is 100% for the OrderID column. Besides, to make inform decisions, I removed all duplicate rows.
![image](https://github.com/user-attachments/assets/7bfa2c1b-d146-4fe5-bdc4-8d99f0b48230)
Manipulate similarly with **Purchases** and **Countries** table.<br>
Lastly, Create **Exchange Rate** table. Select **Get Data**, choose **Python** script, and then add follow script:
![image](https://github.com/user-attachments/assets/11d209f9-c32c-4b0d-afac-e986664b54b4)

### 2. Design and develop a data model
Access to **Model View** in Power BI to view the report's tables.<br> At first step, I created relationships between these tables:<br>
- Create a relationship between the **Countries** and **Exchange** Data tables on the **Exchange ID** field by setting the Cardinality to One to One (1:1) and the Cross filter direction to Both to be bi-directional.<br>
- Create a relationship between the **Sales** and **Countries** tables on the **Country ID** field and set the Cardinality to Many to One (*:1) and cross-filter direction to Both so that it’s bi-directional.<br>
- Create a relationship between the **Purchases** and **Sales tables** on the **OrderID** field, set the Cardinality to One to One (1:1) and cross filter direction to Both to be bi-directional.<br>

Secondly, to make **Time intelligence** caculations, I configured the **Calendar table** and marked it as **date table**. I selected **New Table** and add the following DAX code to create a new **Calendar** table
![image](https://github.com/user-attachments/assets/1db1a6a2-c57e-404c-949b-bf5a98649188)

- Create a relationship between the **Calendar** and **Purchases** tables on the **Date** field, I set the Cardinality to Many to One (*:1).<br>

Here is the final Model and relationships between these tables:
![image](https://github.com/user-attachments/assets/92e0c3ac-3903-4f01-bdde-c5152cf854f9)
 
### 3. Create reports
### Please click on "Bài thuyết trình Tailwind Trader Project.pdf" to see more details and insights from charts and reports that I created!






