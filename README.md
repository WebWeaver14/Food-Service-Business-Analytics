# Food-Service-Business-Analytics
# Excel Workbook

A multi-branch food-service operations dataset (July–August 2025) with a full set of
Excel-based analyses built on top of it: KPI formulas, gross margin breakdowns, a daily
risk-flagging model, dynamic lookups, and an interactive combo-performance dashboard.

## Overview

The workbook simulates canteen operations across **three branches** — Head Office Café,
Plant 1 Canteen, and Plant 2 Canteen — covering orders, menu items, staff, suppliers,
inventory, waste, and customer feedback. It was built as a structured, day-by-day Excel
skills project, moving from raw transactional data to lookup-driven enrichment,
multi-condition KPIs, margin analysis, conditional risk flags, and a filterable dashboard.

## Sheet Guide

### Core data tables
| Sheet | Rows | Description |
|---|---|---|
| `Orders` | 360 | One row per order — branch, customer type, payment type, shift, discount %, total revenue, combo/discount flags |
| `OrderLines` | 924 | Line-item detail per order — SKU, quantity, unit price/cost, category, line revenue and cost |
| `Menu` | 19 | Menu items with SKU, category (Hot Meal / Snack / Beverage / Dessert), supplier, unit cost and price |
| `Staff` | 30 | Staff roster with role, branch, and hourly rate |
| `Inventory` | 19 | Stock on hand, reorder point, lead time, last restock date per SKU |
| `Suppliers` | 10 | Supplier directory (name, city, phone) |
| `WasteLog` | 120 | Logged waste by date, SKU, quantity, and reason |
| `Feedback` | 220 | Customer feedback by date, branch, rating, and comment |

### Calculation & analysis sheets
| Sheet | Purpose |
|---|---|
| `OrdersCalc` | Order-level cost, gross profit, and gross margin % (SUMPRODUCT/lookup-driven), plus a combo-order ranking helper |
| `KPI Calculations (Day 2)` | Monthly revenue & month-on-month change, shift/branch-filtered revenue, beverage+UPI order counts, average ticket size by shift (SUMIFS/COUNTIFS/AVERAGEIFS) |
| `Gross Margin Analysis (Day 4)` | Revenue by category × branch with % contribution, and a Top 10 SKUs by August revenue (INDEX/MATCH/LARGE ranking) |
| `Daily Performance (Day 5)` | Daily revenue, average feedback rating, average waste cost, and an "At Risk" flag driven by combined revenue/rating/waste thresholds |
| `Dynamic Value Retrieval (Day 6)` | A dynamic INDEX/MATCH lookup tool — pick any SKU and field (Unit Price or Unit Cost) to retrieve the value |
| `Dashboard` | Interactive dashboard with Branch/Shift filters — combo order counts, combo % of orders, average ticket size and gross profit, and a Combo vs Single comparison table |

## Key Techniques Used

- **Lookups & enrichment:** VLOOKUP, INDEX/MATCH (including two-way INDEX/MATCH/MATCH lookups)
- **Multi-condition aggregation:** SUMIFS, COUNTIFS, AVERAGEIFS across date ranges, branches, shifts, and payment types
- **Order-level flag formulas:** SUMPRODUCT-based combo/discount/beverage flags
- **Ranking:** LARGE + INDEX/MATCH for Top-10 SKU rankings
- **Conditional risk logic:** nested IF/OR/AND rules combining revenue, feedback rating, and waste cost thresholds
- **Dynamic, filter-driven reporting:** wildcard-based SUMIFS/COUNTIFS/AVERAGEIFS ("All" filters) feeding an interactive dashboard
- **Excel Tables** throughout for structured references and easier maintenance

## How to Use This Workbook

1. Start with the raw tables (`Orders`, `OrderLines`, `Menu`, etc.) to understand the underlying data.
2. Review `OrdersCalc` to see how cost and margin are derived at the order level.
3. Walk through the calculation sheets in order (Day 2 → Day 6) to see the analysis build up.
4. Use the `Dashboard` sheet's Branch/Shift filters (cells B4 and E4) to explore combo vs. single-item order performance interactively.

## Notes

- All monetary figures are in INR.
- Date range covered: July–August 2025.
- This project was completed as part of the Advanced Excel Internship ("Food Service
  Business Analytics") curriculum from Ivy Professional School.
