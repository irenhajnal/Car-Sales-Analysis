# Car Sales Analysis in Power BI

## Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Data Visualization](#data-visualization)
- [Functions Used](#functions-used)
- [Results and Findings](#results-and-findings)
- [Recomendations](#recomendations)


### Project Overview
---
This data analysis project aims to provide insights into the sales performance of a car dealership that sells various car models. The objective of this projects was to design and develop a dynamic and interactive Car Sales Dashboard using Power BI. The dashboard visualizes critical KPIs related to car sales, helping users understand the company's sales performance over time and make data-driven decisions.

<img width="752" alt="Power BI Dashboard - Overview" src="https://github.com/irenhajnal/Projects/assets/122035130/15a4def3-428b-476c-baeb-10ced033ca18">
<img width="752" alt="Power BI Dashboard - Details" src="https://github.com/irenhajnal/Projects/assets/122035130/2f6e585b-91cf-406d-97eb-e3b2568135fa">

### Data Source
Car Sales: The dataset used for this analysis is the "Car Sales.xlsx" file containing detailed information about each sale made by the company.


### Tools
- Excel - Data Cleaning
- Power BI - Creating Reports

### Data Cleaning and Preparation
In the initiaal data preparation phase, I performed the following tasks:
1. Data loading and inspection
2. Checking for missing values
3. Data cleaning and formatting

### Data Visualization
---
#### KPI’s
The dashboard provides insights into key performance indicators (KPIs) related to the sales data. This enables users to make informed decisions, monitor their progress, and identify trends and opportunities for growth.
  1. Sales Overview:
      - Year-to-Date (YTD) Total Sales
      - Month-to-Date (MTD) Total Sales
      - Year-over-Year (YOY) Growth in Total Sales
      - Difference between YTD Sales and Previous Year-to-Date (PTYD) Sales
  2. Average Price Analysis:
      - YTD Average Price
      - MTD Average Price
      - YOY Growth in Average Price
      - Difference between YTD Average Price and PTYD Average Price
  3. Cars Sold Metrics:
      - YTD Cars Sold
      - MTD Cars Sold
      - YOY Growth in Cars Sold
      - Difference between YTD Cars Sold and PTYD Cars Sold
#### Charts
  1.	YTD Sales Weekly Trend: A line chart illustrating the weekly trend of YTD sales. The X-axis represent weeks, and the Y-axis shows the total sales amount.
  2.	YTD Total Sales by Body Style: Distribution of YTD total sales across different car body styles using a Pie chart.
  3.	YTD Total Sales by Color: Presents the contribution of various car colors to the YTD total sales through a pie chart.
  4.	YTD Cars Sold by Dealer Region: Showcase the YTD sales data based on different dealer regions using a map chart to visualize the sales distribution geographically.
  5.	Company-Wise Sales Trend in Grid Form: A tabular grid that displays the sales trend for each company. The grid showcases the company name along with their YTD sales figures.
  6.	Details Grid Showing All Car Sales Information: A detailed grid that presents all relevant information for each car sale, including car model, body style, colour, sales amount, dealer region, date, etc.

### Functions Used ###
---
**1. Created a calendar table in DAX**: to ensure that all the calendar days are included from the start to the end, as the original dataset my not have data for each and every day. This will give the ability to perform different data operations, such as Year To Date (YTD), Year over Year (YOY), Month to Date (MTD)
   
                 Calendar Table = CALENDAR(MIN(car_data[Date],MAX(car_data[Date]))
  
**2. Time Intelligence Functions**: created new measures using TOTALMTD, SAMEPERIODLASTYEAR, TOTALYTD

                YTD Avg Price = TOTALYTD(AVERAGE(car_data[Price ($)]),'Calendar'[Date])

**3. Filter Functions**: ALLSELECTED

                 Max Point on Area Chart = IF(MAXX(ALLSELECTED('Calendar'[Week]),[Total Sales])=[Total Sales],MAXX(ALLSELECTED('Calendar'[Week]),[Total Sales]),BLANK())

### Results and Findings
The analysis results are summarized as follows:
1. The company's sales have been steadily increasing over the past year, with a noticeable peak during the holiday season.
2. Product category A is the best-performing category in terms of sales and revenue. 

### Recomendations
Customer segment with high lifetime value should be targeted for marketing efforts.


### References
1.Guided Project [YouTube](https://www.youtube.com/watch?v=XnPo5Ft7RzQ)
