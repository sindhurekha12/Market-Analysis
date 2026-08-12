## CDACL-006 · Market Analysis — Understanding Customer Purchasing Behavior

## Project Summary

This project analyzes an e-commerce order dataset (structured after the
Instacart public dataset) to answer 20 questions about customer purchasing
behavior, and turns those findings into marketing recommendations.

- **Database:** `project_orders` (MySQL 5.7.43)
- **Tables:** `orders`, `order_products_train`, `products`, `aisles`, `departments`
- **Approach:** All 20 questions answered via SQL in MySQL Workbench. Because
  MySQL 5.7 does not support window functions, queries use independently
  computed derived tables joined back together instead.

## Files in This Submission

| File | Description |
|---|---|
| `Understanding-Customer-Purchasing-Behavior.pptx` | Main presentation — 9 slides covering methodology, catalog scale, reorder behavior, timing patterns, basket composition, users, recommendations, and conclusion, plus a summary dashboard appendix slide. |
| `Appendix_A_SQL_Queries.docx` | Full SQL for all 20 brief questions, in question order, with each query's result summary. |
| Recorded walkthrough (video) | Narrated explanation of the project and findings, to be recorded and sent alongside the files above. |

## Key Findings (at a glance)

- **63,100** unique users, **21** departments, **~1M** total orders
- **10.53** average items per basket
- **0.60** overall reorder rate; staple aisles (milk, water, eggs, fresh
  produce) reorder at **0.68–0.79**
- Orders peak **10–11am**, strongest days are **Sunday and Monday**
- Average reorder cycle: **~26.7 days**

## Marketing Recommendations

1. **Reward Loyalty** — subscribe-and-save offers on high-reorder staples
   (milk, eggs, fresh fruit)
2. **Time Promotions** — schedule ads ahead of the 9am–2pm / Sun–Mon peak
   shopping windows
3. **Grow the Basket** — cross-sell high-margin items on weekends, when
   baskets run slightly larger
4. **Reward Power Users** — loyalty tier / early-access program for top-order
   customers

## Notes & Caveats

- The "missing" aisle (1,254 products) is a genuine aisle label present in
  the source dataset, not a data quality issue.
- The top-10 reorder-rate list (Q4) uses a volume floor of
  `HAVING COUNT(op.order_id) >= 50` to exclude low-volume statistical noise.
- The 100-orders-per-user cap seen in Q19 / Slide 7 is likely a dataset
  artifact rather than a real behavioral ceiling — flagged as a caveat rather
  than a confirmed finding.
- Q7/Q15 and Q11/Q14 are intentionally identical query pairs — the brief asks
  for the same underlying pattern from two different angles.

## Submission Checklist

- [x] PPTX presentation
- [x] Appendix A (full SQL + results)
- [ ] Recorded walkthrough video (PowerPoint: Record Slide Show → Export as Video)
- [ ] Combine and send all files together per the brief's submission instructions
