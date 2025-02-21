# 📊 Provide Insights for Management in Consumer Goods Domain

This project is part of the Codebasics Monthly Resume Challenge #4, where I analyzed business data using SQL and present meaningful insights in a structured and engaging format.

📌 [Challenge Link](https://codebasics.io/challenge/codebasics-resume-project-challenge/7)   
🔗 [LinkedIn Post]()

## 📝 Problem Statement

In this challenge, I stepped into the role of a **junior data analyst** for **Atliq Hardwares** (an imaginary company). Atliq is a leading computer hardware manufacturer in India, but their management struggles with data-driven decision-making due to a lack of clear insights.

To address this, they are expanding their data analytics team and have set up this challenge to evaluate candidates on their SQL expertise and business storytelling skills.

My goal? To analyze their **sales**, **pricing**, and **customer data**, **extract meaningful insights**, and **present them in a compelling way** for top-level management! 🚀

## 🎯 My Approach

Here's how I tackled this challenge step by step:
- 📄 **Understanding Business Needs** – I reviewed the 10 ad-hoc business requests that required insights.
- 🔍 **Running SQL Queries** – I used SQL to fetch relevant data from multiple tables.
- 📊 **Creating a Management Dashboard** – I transformed raw data into clear, actionable insights for executives.
- 🎥 **Presenting Findings Creatively** – I designed an engaging presentation, incorporating charts, visuals, and storytelling for impact.

## 📂 Dataset Details

Before diving into the analysis, it's essential to understand the structure of the data. Here's a breakdown:

### 🔹 Dimension Tables

Dimension tables contain descriptive/static data that help categorize and define the facts.

#### <ins>dim_date</ins> (NEW! 🗓️)

I created this additional table to facilitate time-based analysis efficiently.
- 📅 `date:` Covers a range of fiscal years from 2020 to 2021.
- 📊 `fiscal_year:` Since the company's fiscal year starts in September, the data follows the fiscal years 2020 & 2021.
- 📆 `quarter:` Represents the quarter corresponding to the fiscal year.
- 🏛️ `fy_month_num:` Maps the fiscal month order (e.g., September = 1, October = 2, etc.).

#### <ins>dim_customer</ins>

Contains details about customers and their market presence.
- 🏬 `customer:` Name of the customer (e.g., Atliq Exclusive, Flipkart, Surface Stores).
- 🌍 `platform:` The channel used to sell products (E-Commerce or Brick & Mortar).
- 📦 `channel:` How the product reaches the end consumer (Retailers, Direct, Distributors).
- 🗺️ `market:` Country where the customer is located.
- 🌎 `region:` Broader classification (APAC, EU, NA, LATAM).
- 🏢 `sub_zone:` Sub-region within a market (India, Southeast Asia, Australia & New Zealand).

#### <ins>dim_product</ins>

Contains product-related information.
- 💻 `product_code:` Unique identifier for each product.
- 🏷️ `category:` Product classification (e.g., Peripherals, Accessories, Notebook, Storage, Networking).
- 🖥️ `division:` High-level classification (PC, Network & Storage, Peripherals & Accessories).
- 📦 `variant:` Differentiates product versions (Standard, Plus, Premium).

### 🔹 Fact Tables

Fact tables contain transactional and measurable data, such as sales, pricing, and costs.

#### <ins>fact_sales_monthly</ins>

Tracks monthly sales of each product.
- 📅 `date:` The month in which the sale occurred (fiscal years 2020 & 2021).
- 🛒 `customer_code:` Unique identifier for the customer who purchased the product.
- 📦 `product_code:` Unique identifier for the sold product.
- 📊 `sold_quantity:` Number of units sold.

#### <ins>fact_gross_price</ins>

Holds pricing data for each product.
- 📆 `fiscal_year:` The fiscal year for which the gross price is recorded.
- 💰 `gross_price:` The initial selling price of a product before any deductions.

#### <ins>fact_manufacturing_cost</ins>

Tracks production costs per product.
- 📆 `cost_year:` Fiscal year in which the product was manufactured.
- 🏭 `manufacturing_cost:` The total production cost incurred, including raw materials, labor, and overhead expenses.

#### <ins>fact_pre_invoice_deductions</ins>

Contains discounts applied before invoicing.
- 🛍️ `customer_code:` The customer receiving the discount.
- 📅 `fiscal_year:` The fiscal year for the discount.
- 🔻 `pre_invoice_discount_pct:` Percentage discount applied before invoice generation.

## 🗂️ Data Model
To enhance my analysis, I designed the following data model, integrating the dim_date table to link sales data with time-based insights:

<p align="center">
    <img src='https://github.com/Arindam430/Ad_Hoc_Insights_SQL/blob/main/Resources/Data%20Model.png' height="400">
</p>
