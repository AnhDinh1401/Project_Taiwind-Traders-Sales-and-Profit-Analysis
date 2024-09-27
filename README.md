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
 
### 3. Using DAX to create caculated columns, measures and then creating report
#### 3.1 Creating sales report
Firstly, I created 3 card visualizations to show overall **sales status** of **Taiwind Trader** including **Total Revenue in USD**, **Units Sold** and **Average Rating**:
- **Total Revenue in USD** not available so I used DAX to create measure that caculates it by taking **Total Revenue** field multiple **Exchange Rate** field.<br>
![image](https://github.com/user-attachments/assets/831f8f4d-62b9-4b5b-bee1-c77ea19174b1)

Secondly, I created line chart to illustrate **Total Revenue** overtime by selecting **Visualization Pane** and drag **Purchase Date** to **X-axis** and **Total Revenue in USD** to **Y-axis**.
![image](https://github.com/user-attachments/assets/ca92d150-f8b3-4ee4-b47e-1d943ebb0579)
<br>
Besides, to know how well the sales in each country, I created a **Loyalty Points** column chart and **Total Revenue by Country** pie chart:<br>
![image](https://github.com/user-attachments/assets/1e412335-9dc4-47e9-81ed-acd0763c0755) 
![image](https://github.com/user-attachments/assets/0f289951-e466-4c26-91ef-48d96f53d9c8) 
Lastly, I add a bar chart to the report to know **Units sold by Product Category**<br>
![image](https://github.com/user-attachments/assets/8395069c-5299-496b-aeb7-38a2b8cd1593)
Moreover, I add a slicer to filter the report by **order** status. After all, I resize these visualizations depending on it's importance and rearrange their layout properly. And here is the final results. <br>
![image](https://github.com/user-attachments/assets/4bb3a2ca-356f-4c88-aae7-c7cfb04a6031) 

#### 3.2 Creating profit report
To see this more detail, you could download my **Capstone project final**.<br>
![image](https://github.com/user-attachments/assets/f0529c54-0bc9-47a9-a7dc-84e1cc01f9ab)








