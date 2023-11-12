<article align="center">

![LinksHub-Banner](https://s3.eu-west-1.amazonaws.com/redsys-prod/articles/834af42a1deaacd591e68f97/images/teaserImage_xxxx_Shutterstock_71579725_1662630618746.jpg)
</article><hr>

<a name="welcome-coffee-bean"></a>

# Coffee-Bean-Sales-Excel-Portfolio
_**A Trip Through Data to Unlock the Hidden Potential of Coffee**_
- - The Coffee Bean Sales Dataset provides an extensive view of sales, customer profiles, and details about coffee products, enabling a multifaceted investigation of the booming coffee industry.

## Author
- [@SFutureAnalyst](https://github.com/SFutureAnalyst)

## Table of Contents
- [Problem with Business](#problem-with-business)
- [Source of Data](#data-source)
- [Purpose, Mean, and Conclusion](#purpose-mean-and-conclusion)
- [Method](#method)
- [A Fast Look At The Dashboard](#a-fast-look-at-the-dashboard)
- [Overview of Data](#data-overview)
- [Step-by-Step Modifications](#step-by-step-modifications)

## Problem with Business
**Business Problem Statement:** <br>
Finding the best customers, keeping an eye on coffee-related sales trends, and country-by-nation sales analysis are the major objectives. The dashboard ought to facilitate consumer interaction and loyalty programs, enhance product offers, and assist with efforts to expand geographically.

## Purpose, Mean, and Conclusion
**Overall Objectives:** <br>
- Determine the **top 5** clients.
- Monitor sales patterns similar to those of coffee to improve inventory control.
- To support expansion, analyze sales by nation.

**Solution Requirements:** <br>
- A dashboard that is easy to use and visually appealing.
- Interactive trend identification visualizations.

**Expected Outcomes:** <br>
With the help of the Coffee Sales Dashboard, businesses can increase revenue, enhance customer satisfaction, and spearhead strategic growth initiatives.

## Data Source
- [Coffee Beans Sales Dataset](https://www.kaggle.com/datasets/saadharoon27/coffee-bean-sales-raw-dataset)

## Method
- Exploratory data analysis (EDA)

## A Fast Look At The Dashboard
![dashboard](Assets/Glance.png)

## Data Overview
Data on coffee bean sales are divided into 3 separate sheets:
| **Sheet Name**     	            | **Column Names**     |
|-------------------	        |------------------	       |
| **Orders**     	                | Order ID (Primary Key)<br>Order Date<br>Customer ID<br>Product ID<br>Quantity Ordered                                                            |
| **Customers**    	              | Customer ID (Primary Key)<br>Customer Name<br>Email<br>Phone Number<br>Address Line 1<br>City<br>Country<br>Postcode<br>Loyalty Card         |
| **Products**               	    | Product ID (Primary Key)<br>Coffee Type<br>Roast Type<br>Size<br>Unit Price<br>Price Per 100g<br>Profit 	                                     |

## Step-by-Step Modifications

**Data Gathering and Cleaning:**<br>
In order to generate a comprehensive table that contains all the information about product orders and to improve the data's usability for further analysis, a number of columns from the _Customers_ and _Products_ tables have been combined into the _Orders_ table. These combined columns facilitate a more cohesive representation of the information pertaining to product orders, allowing for more effective analytical processes.

**Columns selected are:**

| **Customers Sheet** |
|-------------------	|
| Customer Name     	|               
| Email    	          |
| Country             |
                                
| **Products Sheet** |
|------------------	 |
| Coffee Type|
| Roast Type |
| Size       |
|Unit Price  |

The techniques employed to retrieve data from the _Customers Table_ involve the utilization of the **VLOOKUP formula**. Meanwhile, a combination of the **INDEX** and **MATCH** functions is applied to extract information from the _Products Table_. This approach ensures that a uniform formula can be adapted and applied across every column within the table, enabling the extraction of data in a consistent manner.

**Adjustments and Column Treatment:**
- 1.	**Email Column:** The missing values in the _Email column_ were replaced with an empty cell using an **IF statement**.
- 2.	**Sales Column:** To populate the _sales column_, a multiplication between _Quantity_ and _Unit Price_ was done
- 3.	**Coffee Type Name Column:** Recognizing that the _Coffee Type column_ exclusively contains abbreviations such as _Rob, Exc, Ara,_ and _Lib_, a supplementary column titled _Coffee Type Name_ has been established. To map the abbreviations to their respective full names, a **Nested IF function** has been implemented. This function systematically converts _"Rob"_ to _"Robusta", "Exc"_ to _"Excelsa"_, _"Ara"_ to _"Arabica"_, and _"Lib"_ to _"Liberica"_, thereby enhancing the comprehensibility of the coffee types.
- 4.	**Roast Type Name Column:** A similar approach was extended to the _Roast Type Name column._ Employing a comparable technique, abbreviations were replaced with their corresponding full roast-type names. Specifically, _"M"_ was transformed to _"Medium"_, _"L"_ denoted _"Light"_, and _"D"_ was indicative of _"Dark"_.
- 5.	**Order Date Column:** To mitigate potential confusion arising from varying date formats across different regions, a strategic adjustment was made. The month component, previously represented as a numeric value, has been transformed into a categorical value.
- 6.	**Size Column:** The _Size column_ lacked metric value notation. As a solution, the unit _"kg"_ was uniformly appended to each row within this column.
- 7.	**Unit Price and Sales Column:** Changed to currency and _$_ symbol was added.
- 8.	**Loyal Card:** Added a new column that checks whether the customer has a loyalty card or not.

**Extra Adjustments**
- Checked all columns in the Data Tab for duplicate variables, and no duplicate entries were found.
Converting the whole data range into a table format called _"Orders"_ was done before plotting pivot charts and tables. One benefit of this transformation is that it will automatically update the pivot table and graphs with any changes made to the dataset in the future, saving you the trouble of making manual adjustments. Data analysis procedures are more accurate and efficient as a result of this dynamic synchronization.

**The Dashboard and Pivot Table:**
- **Total Sales Sheet:**
  - A pivot table titled _"TotalSales"_ was generated with the purpose of visually representing the aggregate sales across different time periods. However, an issue emerged wherein the data was initially grouped by years. To address this, a modification was made by reorganizing the data into _monthly_ and _yearly_ groups. This adjustment enables more detailed visualization of sales trends over time, facilitating a finer granularity for analysis.
  - Proceeded by adding the _"Coffee Type Name"_ and _"Sales"_ columns to the column list and values respectively of the pivot table. These columns will be utilized along the _Y-axis_ for plotting against the date. This aims to provide insights into the quantity of sales recorded on specific dates, while also considering the different coffee types involved. 
  - Inserted a _2D Line Chart_ and formatted it to my satisfaction.
  - Inserted a Timeline feature from the PivotChart Analyzer. This Timeline tool offers the capability to analyse specific segments of the timeline under consideration. By utilizing this feature, one can dynamically narrow down the timeframe of interest within the pivot chart, thereby enhancing the precision of the analysis and facilitating the exploration of particular time intervals in a more focused manner.
  - Inserted 3 Slicers, _Size, Roast Name Type,_ and _Loyalty Card_.

- **Sheet with Country Bar Charts:**
  - Added a new bar graph to represent the countries with the highest sales figures in descending order.
- **The Top Five Clients:**
  - Added a new bar graph and added customer names to the axis category, sorted the whole data in descending order, and then applied the _top 5_ filter.
- **The Sheet with Bar Charts:**
  - Created a new sheet named _“Dashboard”_, where the interactive visuals will be presented.

Finally, created links between each slicer and the different visual components that are there. When filters are applied through the slicers, this linkage makes sure that the changes that follow are automatically reflected on all related graphs and visual representations.
