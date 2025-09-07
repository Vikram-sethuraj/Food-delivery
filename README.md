**Delivery Delay & Performance Analysis – Power BI**

This project showcases a Power BI dashboard analyzing food delivery performance using a public dataset. The dashboard provides insights into delivery time, order types, vehicle efficiency, and customer ratings to identify key factors causing delays.

📌 **Problem Statement**

-Food delivery companies face challenges in monitoring on-time delivery performance.

-Delivery delays impact customer satisfaction and ratings.

-It’s difficult to compare vehicle types, order categories, and delivery distances without interactive reporting.

-Companies lack clear visibility into average delivery time by order type and vehicle, making it harder to optimize operations.

🛠️ **Tools & Technologies**

-Power BI (Dashboard, Visualization, KPI Cards, Slicers)
-SQL (Data Cleaning, Joins, Filtering)

-DAX (Measures, Calculations for KPIs)

-Data Modeling (Star Schema: Orders, Customers, Vehicles, Ratings)

🔄 **Process Overview**

1. **Data Source**
 
 Delivery dataset containing order type, vehicle type, delivery location, time taken, and ratings.

2. **Data Cleaning (SQL)**
 
-Removed nulls and duplicates.

-Standardized categorical fields (e.g., vehicle types, order categories).

-Created a unified delivery dataset.

-- Remove null delivery times

SELECT * FROM delivery_data WHERE Delivery_Time IS NOT NULL;

-- Standardize vehicle type names

SELECT Vehicle_ID, UPPER(TRIM(Vehicle_Type)) AS Clean_Vehicle FROM vehicle_data;

-- Join delivery with order and vehicle tables

SELECT d.Order_ID, d.Delivery_Time, o.Order_Type, v.Vehicle_Type, r.Rating
FROM delivery_data d

JOIN order_data o ON d.Order_ID = o.Order_ID

JOIN vehicle_data v ON d.Vehicle_ID = v.Vehicle_ID;

3. **Data Modeling**
 
-Built a star schema with one fact table (Deliveries) and multiple dimension tables (Orders, Vehicles, Ratings, Locations).

4.**DAX Measures**

-Average Delivery Time

-Average Customer Rating

-Delivery Count by Vehicle Type

-On-time vs Delayed Orders

5.**Dashboard Features**

-Maps: Restaurant vs Delivery Location.

-KPIs: Average Delivery Time (26.32 mins), Average Rating (4.63).

**Visuals:**

-Delivery time distribution by bins.

-Average delivery time by vehicle type (motorcycle, bicycle, scooter, e-scooter).

-Average delivery time by order type (meal, snack, buffet, drinks).

-Filters/Slicers: Order Type, Vehicle Type, Delivery Time Range, Ratings.

✅ **Solution**

-Designed an interactive Power BI dashboard to track delivery delays and performance.

-Provided insights into which vehicle types are faster and which orders take longer.

-Helped identify improvement areas by comparing delivery time bins and customer ratings.

-Enabled real-time analysis for managers to improve customer satisfaction and delivery efficiency.
