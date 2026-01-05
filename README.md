Online Sales Data Analysis
Overview
This project analyzes an online sales dataset to understand customer behavior, sales performance, and product profitability. The work covers data cleaning, feature engineering, exploratory data analysis (EDA) with Python (pandas, seaborn, matplotlib), and dashboarding in Power BI.

Dataset
File: online_sales_clean.csv
Each row represents a single order line from an online or in‑store transaction.

Key columns:

InvoiceNo – Unique invoice number for the transaction.

StockCode – Product stock keeping unit (SKU).

Description – Product description (e.g., “Notebook”, “USB Cable”).

Quantity – Number of units ordered.

InvoiceDate – Date and time of the transaction.

UnitPrice – Price per unit.

CustomerID – Unique customer identifier.

Country – Customer’s country.

Discount – Applied discount (0–1).

ShippingCost – Shipping charge for the order.

PaymentMethod – Payment channel (Credit Card, Paypall, Bank Transfer, etc.).

SalesChannel – Online or In-store.

Category – Product category (Electronics, Furniture, Stationery, Apparel, etc.).

OrderPriority – Priority level (Low, Medium, High, etc.).

Revenue – Discounted revenue from the line item.

NetProfit – Revenue minus shipping cost.

TotalSales – Gross sales before discount.

NetSales – Sales after discount.

DiscountAmount – Monetary value of the discount.

TotalPrice – Final price including shipping.

Year, Month – Date features derived from InvoiceDate.

CustomerSegment – Segmentation (Bronze/Silver/Gold/Platinum) based on TotalSales.

Margin – Profit margin percentage.

LossFlag – Indicates if the order is loss‑making (YES/NO).

Raw data issues handled include invalid dates, non‑numeric values, negative quantities, extreme prices, and inconsistent text labels.

Objectives
Clean and validate online sales data for reliable analysis.

Engineer business features (revenue, profit, segments, recency) useful for decision‑making.

Explore sales patterns by time, country, category, and customer segment.

Visualize insights using seaborn/matplotlib and Power BI dashboards.


Data Cleaning & Feature Engineering
Implemented in Python using pandas:


Type conversion for dates and numeric fields.

Removal of invalid records (missing keys, negative/zero Quantity, unrealistic UnitPrice, invalid Discount).

Standardization of categorical fields (e.g., PaymentMethod, Category).

Business metrics:

Revenue = UnitPrice × (1 − Discount) × Quantity

NetProfit = Revenue − ShippingCost

TotalSales, NetSales, DiscountAmount, TotalPrice

Date features: Year, Month (3‑letter labels).

Customer features: CustomerSegment via quartiles, Margin, DaysSince, LossFlag.

The cleaned output is stored as online_sales_clean.csv and used for both Python EDA and Power BI modeling.

Exploratory Data Analysis (EDA)
Using seaborn and matplotlib, the project explores:

OrderPriority distribution – Count of orders by priority.

Price–volume relationship – Scatter plots of UnitPrice vs Quantity colored by Category.

Category performance – Bar plots of total Quantity and TotalPrice by Category.

Seasonality – Line plots of monthly TotalPrice by Year.

Profitability – Box/violin plots of NetProfit and TotalPrice by Country, Category, and OrderPriority.

Customer behaviour – Distributions of Quantity, UnitPrice, and TotalSales, plus KDE plots by Month and CustomerSegment.

Geography & payments – Pie charts for order share and profit share by Country, and distribution by PaymentMethod.

These visuals highlight top‑performing categories, countries, and customer segments, as well as loss‑making orders and shipping‑cost impact.

Power BI Dashboard
A Power BI report built on online_sales_clean.csv includes:


KPI cards: Total Revenue, Total Net Profit, Number of Customers, Average Order Value.

Treemap: TotalPrice by Category and Country.

Time series: Monthly revenue by Year.

Customer view: Segment contribution (Bronze/Silver/Gold/Platinum).

Operations view: Orders by SalesChannel and OrderPriority; average ShippingCost by ShipmentProvider.

The report allows interactive filtering by date, country, category, and customer segment to support business decisions.
