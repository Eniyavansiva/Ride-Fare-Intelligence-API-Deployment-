### NYC Uber Fare Intelligence Dashboard
Link: [here](https://nyc-uber-fare-intelligence-dashboard.netlify.app/)
### Conclusion

This project delivers an end-to-end NYC Uber fare prediction pipeline, moving from raw ride records to a deployable FastAPI model service. The final workflow is designed to be practical, interpretable, and leakage-safe, with feature engineering and deployment logic aligned so that predictions can be made from raw trip inputs.

Key outcomes:

- Built a clean fare prediction pipeline on 200K NYC Uber ride records, retaining 95.4% high-quality trips after handling invalid coordinates, zero-distance rides, unrealistic fare-distance combinations, and UTC-to-New York local time conversion.
- Applied robust anomaly filtering using `fare_per_km` percentile validation to remove corrupted fare behavior while preserving genuine long-distance, airport, and high-variance ride patterns.
- Engineered high-value predictive features including Haversine distance, coordinate deltas, cyclical time encodings, airport proximity, airport-trip flags, demand-based peak-hour indicators, and pickup/dropoff location clusters.
- Maintained a leakage-safe ML workflow by removing target-derived features before training, deriving peak-hour behavior from demand only, and fitting route clusters on training data before applying them to test data.
- Validated business signals through controlled statistical testing and Chi-square analysis, confirming an independent airport fare premium of approximately $4.75 and identifying meaningful demand-based peak-hour behavior.
- Compared baseline and tree-based models, with XGBoost delivering the strongest performance at R² = 0.927, MAE = $1.42, and RMSE = $2.44.
- Deployed the trained model using FastAPI with `/predict` and `/health` endpoints, allowing users to submit only raw ride inputs while the API automatically computes engineered features before returning a fare prediction.

Overall, the project demonstrates a complete real-world data science workflow: data cleaning, feature engineering, exploratory analysis, hypothesis testing, model development, evaluation, and production-style API deployment.

<img width="1449" height="640" alt="image" src="https://github.com/user-attachments/assets/4fb930fd-f498-4e7d-9ac6-f4863447431d" />
<img width="298" height="127" alt="image" src="https://github.com/user-attachments/assets/51f1a0a5-2443-4bb9-be3e-1cd6ce0462cb" />


