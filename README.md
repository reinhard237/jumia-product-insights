# Jumia Product Performance Dashboard (Excel)

## Project Overview

The **Jumia Product Performance Dashboard** is an exploratory Microsoft Excel project that examines product pricing, discounts, customer ratings, and review activity using a dataset of Jumia product listings. It turns the product-level data into a set of summary tables, product rankings, charts, and dashboard KPIs that make it easier to compare prices and discounts and explore how discounts and customer feedback relate to one another.

The workbook is designed as a product-performance analysis and Excel dashboard project. It is not connected to Jumia's live platform, and the workbook does not record a precise data-extraction date or source URL for each listing.

## Project Objectives

The project aims to:

- Summarize the number of products and the overall pricing and discount position of the dataset.
- Group products into price ranges to understand the distribution of listed products by current price.
- Calculate and categorize the discounts applied to products.
- Compare available customer ratings and review counts across discount categories.
- Identify products with the highest percentage discounts, the most reviews, and the highest ratings.
- Explore whether discount percentage is associated with the number of reviews and whether products with higher ratings tend to receive more reviews.
- Present the results in a consolidated Excel dashboard for quicker interpretation.

## Business Questions

The workbook is structured around questions such as:

1. How many products are included in the analysis?
2. What is the average current price, average original price, and average discount?
3. How are products distributed across budget, affordable, mid-range, and premium price bands?
4. Which products have the largest percentage discounts?
5. Which products have the highest number of customer reviews?
6. Which products have the highest available ratings, and which have the lowest recorded ratings?
7. Do products with higher discounts also have more customer reviews?
8. Do products with higher ratings tend to have more customer reviews?

## Dataset Description

The analysis-ready dataset contains **115 product records** and the following fields:

| Field | Description |
|---|---|
| `Product` | Product title as recorded in the listing data. |
| `Current price` | Current listed selling price, in Kenyan shillings (KSh). |
| `Old price` | Previous/original listed price, in KSh. |
| `Price Range` | Price segment derived from the current price: Budget, Affordable, Mid-Range, or Premium. |
| `Discount Amount (KSh)` | Difference between the old price and the current price. |
| `Discount` | Discount proportion relative to the old price. For example, `0.37` represents a 37% discount. |
| `Review` | Number of customer reviews recorded for the product. This is a review count, not the review text or a sentiment score. |
| `Rating (Numeric)` | Numeric customer rating, where available. |
| `Rating Category` | Rating classification: Poor, Average, Excellent, or Unknown. |
| `Discount Category` | Discount classification: Low Discount, Medium Discount, or High Discount. |

### Derived Categories

The workbook uses the following classification rules:

**Price range**, based on current price:

- **Budget:** below KSh 500
- **Affordable:** KSh 500 to below KSh 1,000
- **Mid-Range:** KSh 1,000 to below KSh 2,000
- **Premium:** KSh 2,000 and above

**Discount category**, based on the discount percentage:

- **Low Discount:** below 20%
- **Medium Discount:** 20% to 40%, inclusive
- **High Discount:** above 40%

**Rating category**, based on the available numeric rating:

- **Poor:** below 3.0
- **Average:** 3.0 to below 4.5
- **Excellent:** 4.5 and above
- **Unknown:** no numeric rating is available

The discount amount is calculated as:

`Discount Amount = Old Price - Current Price`

The discount percentage is calculated as:

`Discount % = (Old Price - Current Price) / Old Price`

## Workbook Structure

The Excel workbook contains seven worksheets:

| Worksheet | Purpose |
|---|---|
| **Dashboard** | Main presentation page. Shows KPI cards for total products, average rating, average discount, and total reviews, alongside visual summaries and product-performance charts. |
| **CleanedData** | Analysis-ready product table containing the ten fields used for the main analysis, including price bands, discount amounts, discount percentages, review counts, rating categories, and discount categories. |
| **Excel Jumia Assignment (2)** | Source/preparation worksheet containing the product-level fields, calculated discount amounts, rating and discount classifications, summary calculations, and helper information for identifying the most and least expensive products. |
| **DISCOUNT COMPARISON CHARTS** | Summary tables comparing average ratings and average review counts across discount categories, and product counts across price ranges. These summaries feed related dashboard visuals. |
| **Sheet3** | Additional summary tables showing average rating and average discount by discount category, together with counts of products by rating category. |
| **PERFORMANCE OF PRODUCT TABLE** | Product-ranking summaries, including the highest-discount products, most-reviewed products, highest-rated products, and lowest-rated products. |
| **TREND ANALYSIS CHART** | Scatter-plot analysis of discount percentage against review count and rating against review count, with written interpretations of the relationships. |

## Dashboard KPIs and Snapshot

The dashboard displays four headline indicators:

| KPI | Value in the workbook | Interpretation |
|---|---:|---|
| Total products | **115** | Number of product records in the analysis dataset. |
| Average rating | **3.89 / 5** | Mean of the 57 products with an available numeric rating. |
| Average discount | **37%** | Mean discount percentage across all 115 product records. |
| Total reviews | **723** | Sum of the recorded review counts for products with available review data. |

The averages and totals should be interpreted alongside the missing-data information below. In particular, the average rating and total review count do not represent all 115 products because many records have no rating or review count recorded.

## Analysis and Key Findings

The current workbook data supports the following descriptive findings:

### 1. Product price distribution

The largest price segment is **Mid-Range**, with 38 products (33.0%). The other segments are:

| Price range | Product count | Share of dataset |
|---|---:|---:|
| Mid-Range | 38 | 33.0% |
| Affordable | 31 | 27.0% |
| Budget | 29 | 25.2% |
| Premium | 17 | 14.8% |

### 2. Discount distribution

High-discount products make up the largest group in the dataset:

| Discount category | Product count | Share of dataset |
|---|---:|---:|
| High Discount | 65 | 56.5% |
| Medium Discount | 32 | 27.8% |
| Low Discount | 18 | 15.7% |

The recorded discount percentages range from 1% to 64%. The largest percentage discount is **64%**, recorded for *6 In 1 Bottle Can Opener Multifunctional Easy Opener*.

### 3. Pricing and savings

Across the 115 records:

- Average current price: approximately **KSh 1,172.79**.
- Average old price: approximately **KSh 1,792.72**.
- Average discount amount: approximately **KSh 619.93**.
- Average discount percentage: approximately **36.96%**.

These are descriptive averages of the product records, not estimates of actual customer savings or sales revenue.

### 4. Ratings and review activity

Only **57 of the 115 products** have numeric ratings and review counts; the other 58 records are marked `Unknown` for these fields.

Among the available records:

- Average numeric rating: approximately **3.89 out of 5**.
- Total recorded reviews: **723**.
- Average review count per product with an available review count: approximately **12.68**.
- The highest review count is **69**, recorded for *120W Cordless Vacuum Cleaners Handheld Electric Vacuum Cleaner*.

The product-ranking worksheet also identifies products with high ratings and low recorded ratings. Rankings should be interpreted carefully where ratings are missing or where multiple products share the same rating.

### 5. Discount levels compared with ratings and reviews

The discount-comparison summaries show the following averages for products with available rating and review data:

| Discount category | Average rating | Average review count |
|---|---:|---:|
| Low Discount | 3.73 | 9.50 |
| Medium Discount | 4.28 | 15.26 |
| High Discount | 3.61 | 11.13 |

In this dataset, the medium-discount group has the highest average rating and average review count among the three discount categories. This is a descriptive comparison only; it does not establish that medium discounts cause higher ratings or more reviews.

## Analysis Workflow

The workbook follows a practical Excel analysis workflow:

1. **Prepare the product data:** organize product titles, current prices, old prices, review counts, and ratings into a consistent tabular structure.
2. **Create calculated fields:** derive discount amounts and classify products by current-price range, discount level, and rating category.
3. **Handle unavailable feedback data:** retain missing rating and review information as `Unknown` rather than treating it as a genuine zero rating or zero reviews.
4. **Summarize the dataset:** use summary and pivot-style tables to calculate product counts and average ratings and review counts by category.
5. **Rank products:** identify products with the largest discounts, the most reviews, and the highest or lowest recorded ratings.
6. **Visualize the results:** use bar, pie/doughnut, and scatter charts to communicate category comparisons, product rankings, and relationships between variables.
7. **Consolidate the findings:** present the main KPIs and charts on the Dashboard worksheet.

## Tools and Excel Skills Demonstrated

The workbook demonstrates the use of:

- Microsoft Excel for data organization and analysis.
- Conditional logic and calculated columns for price, rating, and discount classifications.
- Excel formulas, including `IF`, `AVERAGE`, `MAX`, `MIN`, `INDEX`, and `MATCH` in supporting calculations.
- Summary/pivot-style tables for category-level comparisons.
- Bar charts for product rankings and price-range comparisons.
- Pie and doughnut charts for category summaries.
- Scatter plots for exploring relationships between discount percentage, ratings, and review counts.
- Dashboard design and KPI presentation.

## Data Quality, Assumptions, and Limitations

The results should be read with the following limitations in mind:

1. **Missing feedback data:** 58 of 115 products (50.4%) have `Unknown` values for both rating and review count. Rating and review comparisons therefore use a smaller subset of the dataset.
2. **Repeated product titles:** five product titles appear more than once in the 115 records. These may be repeated listings or duplicate records; they should be checked before deduplication because identical titles do not necessarily prove that two listings are the same product record.
3. **Limited sample:** the workbook analyzes 115 product records and should not be treated as a complete representation of all products on Jumia.
4. **No time dimension:** the workbook does not contain a product capture date or sales-period field. The worksheet named `TREND ANALYSIS CHART` explores relationships across products; it does not show change over time.
5. **No sales or conversion data:** review counts are used as a proxy for visible customer engagement. They are not sales, units sold, revenue, conversion rate, or proof of purchase intent.
6. **Correlation is not causation:** scatter plots can show whether two variables move together in this sample, but they cannot establish that discounts cause more reviews or that ratings cause review activity.
7. **Trendline validation:** the written notes on `TREND ANALYSIS CHART` report R-squared values of approximately 0.00004 for discount percentage versus reviews and 0.1591 for rating versus reviews. A fresh calculation using the 57 numeric pairs in `CleanedData` gives approximate R-squared values of 0.0187 and 0.0033, respectively. These do not match the worksheet notes. The scatter-plot ranges and trendline calculations should therefore be checked before quoting either set of R-squared figures in a formal report.
8. **Source metadata:** the workbook does not include product URLs or an exact collection date. The results should be treated as a snapshot of the data provided for this project, not as current live Jumia prices or ratings.

## How to Use the Workbook

1. Download and open `Jumia Product Performance Dashboard.xlsx` in Microsoft Excel.
2. Start with the **Dashboard** worksheet for the KPI summary and visual overview.
3. Review **CleanedData** to understand the product-level fields used in the analysis.
4. Open the summary and ranking worksheets to see how the dashboard comparisons are supported.
5. Review **TREND ANALYSIS CHART** for the exploratory relationship analysis and its interpretation notes.

If the source data is updated, review the derived categories and summaries, then refresh or rebuild any dependent summary tables and charts. Recheck the missing values and trendline calculations before publishing updated findings.

## Conclusion

This project demonstrates how Excel can be used to transform product-listing data into a structured performance overview. It brings together price segmentation, discount analysis, product rankings, customer ratings, review activity, and dashboard visualization. The analysis suggests that the dataset contains a broad range of discount levels and product price points, while also highlighting the importance of complete customer-feedback data and validated calculations when drawing conclusions.

The project provides a foundation for further work, such as collecting a larger dataset, recording listing dates and URLs, adding product categories, and incorporating actual sales or conversion data to build a more complete view of product performance.
