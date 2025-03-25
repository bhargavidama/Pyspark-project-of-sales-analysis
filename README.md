### Project Overview: Sales Data Analysis and Insights

This project focuses on analyzing sales data to gain insights into customer behavior, product performance, and sales trends over time. The data consists of customer purchase records, including product details and order information. The analysis leverages PySpark to perform data transformations and aggregations on the dataset, uncovering key metrics such as total spend, product popularity, and sales trends by different time periods (e.g., monthly, quarterly, and yearly).

### Key Steps and Features:

1. **Data Loading and Schema Definition**:
   - The sales data and menu data are loaded from CSV files, using custom schemas for both datasets. The sales dataset includes columns like `product_id`, `customer_id`, `order_date`, `location`, and `source_order`. The menu dataset contains details like `product_id`, `product_name`, and `price`.
   - The schema ensures that the data types for each column are correctly interpreted (e.g., `IntegerType` for `product_id` and `price`, `DateType` for `order_date`).

2. **Adding Year, Month, and Quarter Information**:
   - New columns are created to extract the year, month, and quarter from the `order_date` column using PySpark functions (`year`, `month`, `quarter`). These columns help analyze sales patterns over time.

3. **Total Spend by Customer**:
   - The total amount spent by each customer is calculated by joining the `sales_df` and `menu_df` datasets on the `product_id`. The total spend is aggregated by `customer_id` and sorted by `customer_id`.

4. **Total Spend by Product**:
   - The total spend by each food product is calculated by joining the datasets and grouping by `product_name`. This allows for the analysis of which products contribute the most to sales.

5. **Total Sales in Each Month**:
   - Monthly sales are aggregated by `order_month`, giving insights into which months generate the most revenue.

6. **Yearly and Quarterly Sales**:
   - Yearly sales are aggregated by `order_year`, and quarterly sales are aggregated by `order_quarter`. These aggregations provide insights into seasonal trends and year-over-year sales growth.

7. **Product Purchase Frequency**:
   - The frequency with which each product is purchased is calculated by counting the occurrences of `product_id` for each product. This reveals the most popular products among customers.

8. **Top 5 Ordered Items**:
   - The top 5 most ordered items are identified by counting the `product_id` occurrences and sorting them by `product_count`. These items are likely the most popular or in-demand products in the menu.

9. **Frequency of Restaurant Visits by Customers**:
   - The number of distinct visits (i.e., unique order dates) to the restaurant is calculated for each customer who ordered through the "Restaurant" source. This provides an understanding of customer loyalty and frequency of visits.

10. **Most Ordered Product**:
    - The product with the highest number of orders is identified by aggregating the `product_id` and `product_name` and sorting the result. This gives insight into the most popular product in the dataset.

### Conclusion:
The project provides a comprehensive analysis of sales data, focusing on customer behavior, product performance, and sales trends. By using PySpark, we are able to efficiently process large-scale data and extract valuable insights that can be used for business decision-making, such as inventory management, targeted marketing, and identifying popular products.
