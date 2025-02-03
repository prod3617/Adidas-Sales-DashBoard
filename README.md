
# PowerBI Data Analysis

## Adidas Sales Analysis

### Table of Contents

- [Project Description](#project-description)
- [Data Source](#data-source)
- [Data Cleaning](#data-cleaning)
- [Tools](#tools)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results/Findings](#resultsfindings)
  

### Project Description
The project aims to create a comprehensive dashboard to analyze the sales of Adidas. Multiple charts are created according to the sales by product, retailer, region, month to analyze the sales. Various filter option is provided to analyze the sales according to a particular region and time frame.

![Adidas Sales Dashboard Image](Adidas%20Sales%20Dashboard.png)

### Data Source
- Adidas Sales Data: The data is available in the "Adidas US Sales Datasets.xlsx" file which contains all the sales data.

### Tools
- Power BI Desktop: For data cleaning and visualization.

### Data Cleaning
- In the Power BI Desktop, we have inserted the xlsx data. I have checked each column for missing values and formatting issues. I have also checked whether the datatypes assigned to each column are correct. 

### Exploratory Data Analysis
Performed some exploratory data analysis to find some information about key questions like
- Total sales, Operating Profit from the sales.
- Average price per unit and the total unit sold.
- How the sales happening in each month of the year.
- How are the sales happening by region, product, and retailer?
- Which state comes in the top 10 sales?

### Data Analysis
To find the answer to the key questions, I have written some query in the PowerBI as
``` PowerBI
Most Sold Product = 
VAR RegionSales =
    SUMMARIZE(
        'Data Sales Adidas',
        'Data Sales Adidas'[Region],
        'Data Sales Adidas'[Product],
        "TotalSales", SUM('Data Sales Adidas'[Total Sales])
    )
VAR TopProduct =
    TOPN(
        1,
        RegionSales,
        [TotalSales],
        DESC
    )
RETURN
    MAXX(TopProduct, 'Data Sales Adidas'[Product])

```


### Results/Findings
- Sales are high in July, August and December.
- New York, California, and Florida are the top-earning states.
- Sales are high in the west region.
- The most sold product is Men's Street Footwear.
- The top retailer by sale is West Gear.
