# Logistics Fleet Analytics Project

Power BI capstone analyzing profitability, delivery performance, and safety risk across a 120-truck logistics fleet.

## Overview

This project analyzes 14 linked operational datasets — 85,410 loads, 150 drivers, 120 trucks, and 170 safety incidents — to answer three questions for operations leadership:

- Where is the company making and losing money?
- Why is on-time delivery inconsistent?
- Where is cost and safety risk concentrated?

## Key Findings

- **$298.62M revenue, 66% margin** — profitable overall, but the margin hides real losses underneath.
- **$8.7M lost on 11,664 loads (15%)** — these loads cost more in fuel than they earned, spread evenly across every customer and load type.
- **44.6% on-time delivery rate**, flat for 3 years across every terminal, customer type, and driver experience level — pointing to a systemic scheduling issue rather than a performance problem tied to any one location.
- **10 active drivers account for 30% of all safety claim cost** ($2.65M total claims across 170 incidents) — a small, specific, addressable group.

## Tools & Approach

- **Power BI**: star-schema data model, DAX measures for revenue, margin, rate variance, on-time delivery rate, and incident risk
- **SQL**: querying the same dataset (`fleet.db`, SQLite) to validate and cross-check dashboard figures
- Four-page dashboard: Financial Overview, Fleet Operations & Maintenance, Driver & Delivery Performance, Safety & Risk

## Files in this repo

| File | Description |
|---|---|
| `Logistics_Fleet_Analytics_Writeup.docx` | Full written report: findings, insights, and recommendations |
| `fleet.db` | SQLite database of all 14 source tables, for SQL practice and verification |
| Dashboard screenshots | Financial, Fleet, Driver, and Safety pages |

## Recommendations

1. Audit delivery scheduling against realistic transit times
2. Set a minimum rate-per-mile floor to stop loss-making loads
3. Re-price the lowest-margin lanes
4. Review the 28 idle trucks for repair-or-retire decisions
5. Target safety coaching at the 10 highest-risk active drivers

---
**Author**:Ndibueze Esther Mmesoma | [LinkedIn](https://www.linkedin.com/in/esther-ndibueze-418646297)
