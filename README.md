### Conclusion
This project improves fare prediction by strengthening feature quality while keeping a clean, leakage-safe ML workflow.

What changed in this rework:
- Added focused data quality checks (near-zero fare anomaly removal and NYC coordinate bounds).
- Added precision and geometry features: `haversine_km_exact`, `delta_lat`, `delta_lon`, `manhattan_proxy_km`.
- Added time-cycle features: `hour_sin`, `hour_cos`.
- Added airport-context features: `pickup_airport_dist_km`, `dropoff_airport_dist_km`, `airport_trip`.
- Preserved strict order: train/test split first, then train-only route clustering.

Performance summary:
- Earlier runs in this project were around `R2 = 0.63` to `0.66`.
- After the rework, tuned XGBoost reaches about `R2 = 0.735` on the held-out test split.
- Cross-validation remains stable in the low `0.72` range, showing consistent generalization.

Final takeaway:
This pipeline is now cleaner, better structured, and materially stronger in predictive performance within this project setup.

<img width="2770" height="1375" alt="image" src="https://github.com/user-attachments/assets/dd437524-c92d-4adc-9a8c-a81a1b639dda" />
<img width="2761" height="1276" alt="image" src="https://github.com/user-attachments/assets/c9ad8eb5-d37e-4546-9cc1-7e283dbdf56c" />
<img width="1097" height="249" alt="image" src="https://github.com/user-attachments/assets/70e8a8ac-afdb-4acf-82d0-fdfd88609650" />
