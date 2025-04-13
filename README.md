# Fresh Foods Supermarket Inventory Management Dashboard Project

## Project Background

Fresh Foods Supermarket is a regional grocery chain operating across several neighborhoods. Established in 1995, Fresh Foods has built a reputation for providing fresh produce, quality meats, and a wide variety of grocery items to its local communities. Their business model relies on efficient inventory management to ensure product availability for customers while minimizing waste and storage costs. Key business metrics that Fresh Foods closely monitors include daily and monthly sales revenue, inventory turnover rate, stockout rate for popular items, and the cost of goods sold.

As a Data Analyst at Fresh Foods Supermarket, I was tasked with developing a solution to automate and enhance our inventory management processes. The goal was to create a centralized, interactive dashboard that provides real-time insights into our inventory levels, sales trends, and replenishment needs, empowering managers to make data-driven decisions.

Insights and recommendations are provided on the following key areas:

* **Overall Inventory Visibility:** Providing a comprehensive view of inventory levels across the warehouse and store shelves.
* **Low Stock Management:** Identifying products with critically low stock to prevent stockouts.
* **Sales Performance Analysis:** Understanding daily and monthly sales trends for various products.
* **Replenishment and Resend Optimization:** Identifying products needing to be ordered or transferred between the warehouse and stores.

The SQL queries used to inspect and clean the data for this analysis can be found here [Link to SQL Queries - Placeholder].

Targeted SQL queries regarding various business questions can be found here [Link to Targeted SQL Queries - Placeholder].

An interactive Tableau dashboard used to report and explore sales trends can be found here [Link to Tableau Dashboard - Placeholder].

## Data Structure & Initial Checks

Fresh Foods Supermarket's main database structure consists of four primary tables: `warehouse_inventory`, `store_inventory`, `sales_transactions`, and `transfer_logs`, with a total row count of approximately 1,500,000 records. A description of each table is as follows:

* **Table: `warehouse_inventory`**
    * Columns: `product_id` (INT, Primary Key), `product_name` (VARCHAR), `quantity_in_warehouse` (INT), `arrival_date` (DATE), `supplier_id` (INT), `expiry_date` (DATE, nullable)
    * Description: Contains records of inventory currently stored in the central warehouse, including product details, quantity, arrival date, supplier information, and expiry date for perishable items.

* **Table: `store_inventory`**
    * Columns: `product_id` (INT, Primary Key), `product_name` (VARCHAR), `quantity_on_shelf` (INT), `last_replenishment_date` (TIMESTAMP), `shelf_location` (VARCHAR)
    * Description: Stores information about the inventory present on the store shelves, including the quantity, the last time it was replenished, and its location within the store.

* **Table: `sales_transactions`**
    * Columns: `transaction_id` (INT, Primary Key), `product_id` (INT), `sale_date` (DATE), `sale_time` (TIME), `quantity_sold` (INT), `sale_price` (DECIMAL)
    * Description: Records every sales transaction, including the product sold, the date and time of the sale, the quantity, and the sale price.

* **Table: `transfer_logs`**
    * Columns: `transfer_id` (INT, Primary Key), `product_id` (INT), `quantity_transferred` (INT), `warehouse_departure_time` (TIMESTAMP), `store_arrival_time` (TIMESTAMP)
    * Description: Tracks all inventory transfers from the warehouse to the store shelves, including the product, quantity, and timestamps for departure and arrival.

[Entity Relationship Diagram here - Placeholder for ERD image]

## Executive Summary

### Overview of Findings

The automated inventory management dashboard provides Fresh Foods Supermarket with a real-time, comprehensive view of their inventory across the supply chain. Key findings reveal opportunities to optimize stock levels by identifying products with low inventory in both the warehouse and on store shelves, enabling proactive replenishment. Furthermore, the dashboard highlights top-selling products and sales trends, empowering managers to make informed decisions about product placement and procurement.

[Visualization, including a graph of overall trends or snapshot of a dashboard - Placeholder for Dashboard Snapshot]

## Insights Deep Dive

### Category 1: Overall Inventory Visibility

**Main insight 1.** The dashboard provides a clear breakdown of total inventory by product, differentiating between stock held in the warehouse and stock available on store shelves. This allows managers to quickly understand the overall inventory position for any given product.

**Main insight 2.** Interactive filters enable users to drill down into specific product categories or individual products, providing a granular view of their inventory distribution.

**Main insight 3.** The dashboard displays the date of the last inventory update, ensuring managers are aware of the freshness of the data.

**Main insight 4.** Visual cues, such as color-coded indicators, highlight products with a significant portion of their total inventory residing in either the warehouse or the store, potentially indicating slow-moving items or the need for shelf replenishment.

[Visualization specific to category 1 - Placeholder for Inventory Overview Visualization]

### Category 2: Low Stock Management

**Main insight 1.** The dashboard features a dedicated section highlighting products with current stock levels below predefined thresholds in both the warehouse and on store shelves. These thresholds can be customized based on product demand and lead times.

**Main insight 2.** An alert system, integrated within the dashboard, visually flags critical low-stock items, enabling immediate attention and action from inventory managers.

**Main insight 3.** The dashboard shows the trend of stock levels over the past week/month for low-stock items, providing context on how quickly the stock is depleting.

**Main insight 4.** Managers can filter the low-stock list by location (warehouse or store) to prioritize replenishment efforts accordingly.

[Visualization specific to category 2 - Placeholder for Low Stock Visualization]

### Category 3: Sales Performance Analysis

**Main insight 1.** The dashboard displays daily and monthly sales revenue trends, allowing Fresh Foods to track overall sales performance and identify peak sales periods.

**Main insight 2.** A leaderboard of top-selling products, updated in near real-time, helps identify popular items and understand customer preferences.

**Main insight 3.** Sales data can be segmented by product category, enabling analysis of the performance of different departments within the supermarket.

**Main insight 4.** The dashboard allows for year-over-year sales comparisons, providing insights into growth trends and seasonality.

[Visualization specific to category 3 - Placeholder for Sales Performance Visualization]

### Category 4: Replenishment and Resend Optimization

**Main insight 1.** By analyzing sales trends and current warehouse stock, the dashboard suggests products that are likely to need replenishment soon, helping to proactively manage orders from suppliers.

**Main insight 2.** The dashboard identifies products with high sales velocity but low store shelf stock, indicating the need for transfers from the warehouse to the store.

**Main insight 3.** Analysis of resend data (products removed due to damage or expiry) helps identify potential issues with storage, handling, or product shelf life.

**Main insight 4.** The dashboard can highlight products with consistently low sales and high warehouse stock, suggesting potential candidates for promotional activities or reduced ordering.

[Visualization specific to category 4 - Placeholder for Replenishment/Resend Visualization]

## Recommendations:

Based on the insights and findings above, we would recommend the Inventory Management and Store Operations teams at Fresh Foods Supermarket to consider the following:

* **Observation:** Several key perishable items frequently appear on the low stock list on store shelves, despite having sufficient stock in the warehouse. **Recommendation:** Optimize the transfer schedule and process for these items to ensure timely replenishment of store shelves, potentially increasing the frequency of transfers during peak demand periods.

* **Observation:** The sales performance analysis reveals a consistent increase in sales for organic produce during the last quarter. **Recommendation:** Consider increasing the shelf space allocated to organic produce and potentially exploring new suppliers to meet the growing demand.

* **Observation:** Certain non-perishable items show consistently high warehouse stock and low sales over the past six months. **Recommendation:** Implement targeted promotional campaigns or consider reducing future orders for these slow-moving items to optimize warehouse space and reduce potential waste.

* **Observation:** The resend analysis indicates a higher-than-average rate of damaged goods for a specific brand of packaged snacks. **Recommendation:** Investigate the handling and storage procedures for this brand, and potentially engage with the supplier to address packaging concerns.

* **Observation:** The dashboard highlights a few products that consistently have low stock in both the warehouse and on store shelves, coinciding with high sales. **Recommendation:** Review the current ordering quantities and lead times for these high-demand items to ensure sufficient stock levels are maintained to avoid stockouts and lost sales.

## Assumptions and Caveats:

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

* **Assumption 1:** The `product_id` is consistent and unique across all four tables, allowing for accurate joining and analysis of inventory movement and sales.
* **Assumption 2:** The timestamps for warehouse departure and store arrival in the `transfer_logs` table are accurate and reflect the actual movement of goods.
* **Assumption 3:** Sales data from the POS system is complete and accurate, capturing all sales transactions without significant errors or omissions.
* **Assumption 4:** The predefined low stock thresholds used in the dashboard are appropriate for the current demand patterns and lead times for each product. These thresholds may need periodic review and adjustment.
* **Caveat 1:** The analysis does not currently incorporate external factors that might influence sales and inventory, such as seasonal events, local holidays, or competitor activities. Incorporating such data in future iterations could provide more nuanced insights.
