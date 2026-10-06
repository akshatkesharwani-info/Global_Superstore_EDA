# Exploratory Data Analysis on Global Superstore

A complete EDA on a global retail dataset to find patterns, trends and business insights using Python, statistics and charts.

## Objective

Understand what drives sales and profit in the Global Superstore data, find where the business is losing money, and give 5 clear business recommendations.

## Dataset

- **File:** `Global_Superstore2.csv`
- **Size:** 51,290 order lines, 24 columns
- **Period:** January 2011 to December 2014
- **Main columns:** Order Date, Ship Mode, Segment, Market, Region, Country, Category, Sub-Category, Product Name, Sales, Quantity, Discount, Profit, Shipping Cost, Order Priority

## Project Structure

```
Global_Superstore_EDA/
|-- Global_Superstore_EDA.ipynb        # full analysis notebook
|-- Global_Superstore_EDA_Report.pdf   # PDF summary of key findings
|-- Global_Superstore2.csv             # dataset
|-- requirements.txt                   # libraries needed
|-- README.md
|-- images/                            # all charts saved as PNG (15 files)
```

## How to Run

1. Download or unzip the project folder.
2. Install the libraries:
   ```
   pip install -r requirements.txt
   ```
3. Open the notebook:
   ```
   jupyter notebook Global_Superstore_EDA.ipynb
   ```
4. Click **Run All**. The charts are saved in the `images` folder.

**Google Colab:** upload `Global_Superstore2.csv` in the Files panel first, then upload and run the notebook.

Keep the CSV in the same folder as the notebook, otherwise the file path will not work.

## What Was Done

**1. Data Understanding**
- Shape, data types, first and last 5 rows
- Data profile (non-null count and unique values for each column)
- Target variables (Sales, Profit) and feature types (numerical, categorical, temporal)

**2. Data Cleaning**
- Missing values: only Postal Code had missing values (80.51%), it only exists for US orders, so it was dropped
- Date columns converted to datetime, extra columns added (Year, Month, Quarter, Ship Days)
- Duplicate rows checked (none found)
- Outliers found with the IQR method for Sales, Profit and Quantity. They are real large orders, so they were kept and capped columns were made for charts

**3. Statistical Summary**
- Descriptive statistics, skewness and kurtosis
- Correlation matrix with heatmap

**4. Visualizations (10 required charts + 5 extra)**
Sales histogram, profit by category, monthly sales trend, regional sales, top 10 products, discount vs profit scatter, quantity by ship mode box plot, category vs sub-category heatmap, segment pie chart, monthly sales vs profit dual-axis chart, plus correlation heatmap, profit by sub-category, profit by region, profit by discount group and seasonality charts.

## Key Findings

- Total sales are about 12.64M and total profit is about 1.47M (11.6% margin)
- **Top 3 categories by profit:** Technology (663,779), Office Supplies (518,474), Furniture (285,205)
- **Tables** is the only loss making sub-category (-64,083)
- **Weak regions:** Southeast Asia (2.0% margin), EMEA (5.5%) and South (8.8%)
- **Biggest loss making countries:** Turkey, Nigeria and the Netherlands
- **Discount vs profit:** correlation is -0.32. Profit turns negative above 20% discount and every order line above 50% discount loses money
- **Seasonality:** Q4 gives 34% of sales, Q1 only 15.7%. Sales and profit grew every year

## Business Recommendations

1. Cap discounts at 20% and add an approval rule above that
2. Fix the pricing and discounts on Tables, or drop the worst products
3. Review Southeast Asia, EMEA and the loss making countries before investing more
4. Focus stock and marketing on Technology and on Q4
5. Move customers to cheaper shipping modes and charge extra for fast shipping

## Tech Stack

- Python
- pandas, numpy
- matplotlib, seaborn
- Jupyter Notebook

## Author

**Akshat Kesharwani**
- Portfolio: https://akshatkesharwani-info.github.io/
- GitHub: https://github.com/akshatkesharwani-info
