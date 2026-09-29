# Excel Sales Intelligence Dashboard

A hands-on Excel project exploring sales, cancellations and delivery performance across 100 sample retail orders. Built by **Pratik Prakash Gawde** to practise data preparation, cross-sheet lookups, PivotTables and dashboard reporting.

## Project objective

Turn transaction-level data into a report that helps answer:

- Which regions, categories and products generate the most sales?
- How do cancellation rates vary across regions?
- How many completed deliveries arrive within two days?
- How do results change when filtering by region, payment method or delivery status?

## Dataset

The course mini-project supplies an Amazon-themed sample retail dataset with 100 transactions and supporting master sheets. This is an educational exercise, not an analysis of verified Amazon business data.

| Sheet | Purpose |
| --- | --- |
| AmazonSales | Order dates, customer and product IDs, quantities, sales amounts, payment methods and fulfillment details |
| CustomerMaster | Customer details matched through Customer ID |
| ProductMaster | Product names and categories matched through Product ID |
| RegionGoals | Supplied regional sales targets; not used in the headline findings below |
| Analysis | PivotTables and supporting calculations |
| Dashboard | Charts, slicers, KPI summaries and reflections |

## Excel features used

- **XLOOKUP:** Retrieve customer names, product names and categories from master sheets, with a visible fallback for missing matches.
- **IF and date calculations:** Calculate delivery time for completed orders and classify deliveries as Fast or Slow.
- **SUM and COUNTIF:** Calculate overall sales and delivery metrics.
- **PivotTables:** Summarize sales by region and category, count order statuses, calculate average delivery time and regional cancellation rates, and summarize delivered sales by month.
- **PivotCharts and slicers:** Explore results by Region, Payment Method and Delivery Status.
- **Conditional formatting:** Highlight comparative results in the analysis.

## Metric definitions

| Metric | Definition |
| --- | --- |
| Total Revenue dashboard card | Sum of Total Amount across all order statuses. This includes cancelled and in-transit orders and represents total recorded order value for this exercise. |
| Effective Sales | Sales amount for Delivered orders only |
| Delivery Time | Delivery Date minus Order Date for completed deliveries; blank otherwise |
| Fast Delivery | A completed delivery taking two days or fewer |
| Fast Delivery Percentage | Fast deliveries divided by all delivered orders |
| Regional Cancellation Rate | Cancelled orders in a region divided by all orders in that region |
| Highest-selling Product | Product ranked by total order value, rather than units sold |

## Findings with all filters cleared

| Measure | Result |
| --- | ---: |
| Total orders | 100 |
| Total recorded order value | 35,258 |
| Effective Sales, delivered orders only | 13,656 |
| Delivered orders | 34 |
| Cancelled orders | 30 |
| In-transit orders | 36 |
| Average completed delivery time | 3.76 days |
| Deliveries within two days | 11 |
| Fast deliveries as a percentage of delivered orders | 32.35% |
| Overall cancellation rate | 30% |

Amounts are shown without an assumed currency.

- **Electronics** leads categories by total order value at **15,209**.
- **Smartphone** leads products by total order value at **9,644**.
- **North, West and South** lead regions by total order value at **10,491**, **8,359** and **7,317**, respectively.
- **North** has the highest cancellation rate at **40%**.
- Ranking regions by delivered sales instead gives **North, West and Central**.

## How to use the workbook

1. Download the `.xlsx` workbook from this repository.
2. Open it in a version of Microsoft Excel that supports XLOOKUP, PivotTables and slicers. Desktop Excel is recommended for exploring the workbook.
3. Open the **Dashboard** sheet.
4. Use the Region, Payment Method and Delivery Status slicers to filter the connected PivotTables and charts.
5. Clear the slicer filters to return to the full dataset.
6. After changing source data, select **Data > Refresh All** to update the PivotTables.
7. Review **Analysis** for supporting summaries and **AmazonSales** for row-level formulas.

The Total Revenue and Fast Delivery Percentage cards use source-table formulas and show overall dataset metrics. They do not change with the PivotTable slicers. Charts and Pivot-linked summaries reflect their connected filters.

## What I learned

Missing delivery dates must not be treated as zero-day deliveries. Doing so included cancelled and in-transit orders in the average and understated delivery time. Restricting the calculation to completed deliveries produced the correct average of 3.76 days.

I also learned to distinguish products from categories, total order value from delivered sales, and deliveries taking exactly two days from those completed within two days. These definitions matter as much as the dashboard's appearance.

XLOOKUP made it easier to connect transaction records with descriptive details without manually searching and copying between sheets.

## Limitations and further improvements

- The sample contains only 100 orders, so its findings should not be generalized to a real retailer.
- Customer ID **CUST050** is absent from the supplied customer master and is flagged as **Not Found**.
- Regional cancellation rates should be compared using a bar chart with the actual rates. Pie-chart shares of summed rates do not represent regional cancellation rates.
- A future improvement is to make the overall KPI cards respond to slicers and add a month filter.
- Further analysis could compare delivery times by fulfillment partner and region. The current results identify delivery performance, but do not establish the causes of delays.

## Author

**Pratik Prakash Gawde**  
MSc Data Analytics student  
[GitHub profile](https://github.com/PratikG091202)

Feedback on the calculations, chart choices and dashboard usability is welcome.
