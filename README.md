# 💳 Credit Card Transaction Analysis Dashboard (Power BI)

This Power BI project analyzes credit card transaction data to uncover key insights into customer spending behavior. It includes interactive visualizations, detailed monthly trends, and category-wise breakdowns, enabling financial analysis and strategic decision-making

## Features & Tools Used

- **Power BI Desktop**: Data modeling, visualization, and dashboard development
- **Power Query**: Data cleaning, transformation, and ETL processing
- **DAX (Data Analysis Expressions)**: Created custom measures for:
  - Total Spend
  - Total Transactions
  - Average Transaction Value
  - Spend by Month
  - Spend by Category
- **Interactive Dashboard** with slicers and filters for user-level analysis


## Questions Explored

# 1️.What is the total credit card spend by Aaron Murray?
* $73.69 million


# 2️.How many transactions were recorded, and what is the average transaction value?

*Total Transactions: 1,000,000
*Average Transaction Value: $70.28


# 3️. Which spending category has the highest value and percentage of total spend?
Answer:
*Category: Shop Online
*Amount: $28.12 million

Percentage: 38.16%
(Shown in the donut chart and category-wise breakdown)

# 4️.How does spending change month to month—what’s the peak spending month?
 Answer:
*Peak Month: December
*Spend in December: Just under $10 million


# 5️. Which months show the lowest transaction values?
 Answer:
*Lowest Months: April, May, and October
*Estimated Spend Range: Around $5 million or less(Based on the bar chart's visual scale)


# 6️. What’s the difference in spend between Shop Online and Entertainment?
Answer:
*Shop Online: $28.12 million
*Entertainment: $13.05 million

Difference: $15.07 million
(Displayed in the category breakdown panel)

# 7️. Is there evidence of seasonal spending spikes (e.g., December)?
 Answer:
 *Yes – December shows a notable spike in spending, suggesting seasonal shopping behavior (likely holiday-related)

# 8️. Which category is the second-highest in terms of spending?

Answer:
*Category: Personal Care

*Spend: $17.68 million(Second to Shop Online in the donut chart and values)


# 9️. How balanced is the distribution of spending across the four categories?

 Answer:
* The distribution is moderately skewed toward Shop Online (38.16%)

* The next three categories range between 17%–24%

 * so, There is some imbalance, with Shop Online being a dominant category.

# 10. If Aaron wants to reduce costs, which category could be optimized first based on volume and impact?

Answer:
*Recommendation: Focus on Shop Online – it has the highest spend ($28.12M) and the greatest impact (38.16%).

*A 10% reduction here alone would save over $2.8M.

# DAX measures used in the Power BI  Project for credit card transaction analysis.

 1.  Total_Spend = SUM(TransactionData[Amount])
 2.  Total_Transactions = COUNT(TransactionData[TransactionID])
 3.  Total_Transactions = COUNT(TransactionData[TransactionID])

We Can Also use Measures like,

Monthly_Spend = 
CALCULATE(
    SUM(TransactionData[Amount]),
    ALLEXCEPT(TransactionData, TransactionData[Month])) Aggregates total spend for each calendar month.



Category_Spend = 
CALCULATE(
    SUM(TransactionData[Amount]),
    ALLEXCEPT(TransactionData, TransactionData[Category])).Returns total spend for each transaction category (e.g., Shop Online, Entertainment, etc.)


Category_Spend_Percent = 
DIVIDE(
    [Category_Spend],
    [Total_Spend],
    0).








