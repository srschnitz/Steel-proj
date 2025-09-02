#Steel-proj
Initial Thoughts:
This project began as an exploration—an opportunity to play with the dataset, discover insights, and refine data analysis techniques. Over time, it has evolved into a portfolio showcasing various methods for wrangling and analyzing data. It has been a journey, and there's still much more to uncover.
![Pin Icon](images/pin.png)
## 🎬 Portfolio Showcase – Gamma App  
This Steel project is now part of a broader analytics portfolio exploring forecasting, regime analysis, and environmental diagnostics.  
Interactive Gamma app:https://gamma.app/docs/Susan-Schnitzel-Portfolio-of-Analysis-of-Steel-Industry-cvmxtigev33ntwm

Key Findings & Analysis
1. Data Cleaning & Exploration
The initial step involved cleaning the raw data, but this remains a dynamic process—new insights often lead to additional refinements.
Hidden patterns and newly created columns continue to emerge, reinforcing the value of iterative exploration.
I prefer to retain columns rather than delete them, ensuring flexibility for future analyses.

2. Integrating Weather Data
Merging weather and environmental data from a location near the steel plant provided a valuable layer for analysis.
The integration enhanced understanding of how weather influences energy usage.
However, there were missing values, and the weather station was not at the exact steel plant location—even small geographic differences can lead to varied conditions.

3. Statistical Insights
Energy & CO₂ Correlations
Exploratory Data Analysis (EDA) using Spearman correlation confirmed a strong relationship (correlation = 0.72, p < 0.001) between Usage_kWh and Lagging_Current_Reactive.Power_kVarh, highlighting electrical inefficiency.
Humidity’s impact on energy: Energy usage spikes above 85% relative humidity, likely due to increased drying energy required for iron ore.
Predictive modeling:
Random Forest modeling (R² = 0.88) identified reactive power and humidity as key drivers of energy consumption.
Working on revamping my other models with adding humidity.  More to come here.  
CO₂ and Energy Usage show strong collinearity, requiring separate models for each response variable.

4. Energy Savings Estimates
Optimizing power factor → Potential energy reduction of 5% (~100,000 kWh/year).
Dehumidification in summer months → Estimated savings of 3% (~15,000 kWh/year).
Load scheduling → Could reduce consumption by 1% (~20,000 kWh/year).

Total projected savings: 135,000 kWh/year, aligning with ENERGY STAR benchmarks (10–20% efficiency improvement in steel plants). 📌 Reference: ENERGY STAR Steel Efficiency Guide.

5. Cost Savings Conjecture
Using an industrial electricity rate of $0.10/kWh (South Korea estimates from KEPCO & IEA), the projected savings amount to:
$10,000/year from power factor optimization.
$1,500/year from humidity adjustments.
$2,000/year from load scheduling.
![Pin Icon](images/pin.png)

Total estimated cost savings: $13,500/year 📌 Reference: IEA Iron & Steel Technology Roadmap.

6. Business & Environmental Impact
These improvements reduce operational costs and CO₂ emissions (approx. 100 tons/year, assuming 0.75 kg CO₂/kWh).
![Pin Icon](images/pin.png)

Sustainability gains: Per ScienceDirect, South Korean steel plants have significant energy-saving potential, validating this approach. 📌 Reference: ScienceDirect Study on Steel Plant Efficiency.

8. Chemistry & Process Considerations
High humidity increases drying energy for iron ore—a chemical process that could be mitigated with dehumidification to save costs.

9. Limitations & Future Directions
The dataset lacks cost data, so savings estimates are based on external benchmarks.

Actual savings may differ due to plant-specific electricity rates and operational constraints.

Further refinement and testing of predictive models will help improve accuracy.
## Steel Industry Energy Optimization
- **Overview**: Reduced energy usage by 17.2% ($20,467.13/year savings) using Random Forest, XGBoost, SARIMAX, and Lean Six Sigma.
- **Key Insights**:
  - Winter peak: 32.08 kWh (raw data, 8,640 rows, $5,911.53 savings).
  - SARIMAX forecast: 19.34 kWh.
  - Kruskal-Wallis test: Significant seasonal differences (Statistic = 1919.11, p = 0.0).
- **Files**: `analysis_script.py`, `plots/`.
- **Visuals**: [Savings by Season](plots/savings_by_season.png), [Savings Table](plots/savings_table.png).
- ##  Random Forest Classifier: CO₂ Diagnostics - added a new notebook (duplicate, but with added code.)

This notebook applies a Random Forest classifier to predict CO₂ classification outcomes, excluding rows with zero energy usage to preserve model integrity. Diagnostics include:

- Confusion matrix with annotated labels  
- ROC curve and precision-recall curve  
- TPR/FPR analysis across thresholds  
- SHAP feature importance, beeswarm, and dependence plots  

These visuals support interpretability and align with Six Sigma principles of transparency and root cause analysis.
[View the notebook](./Random%20Forest%20Classifier:%20Model%20Training/Analysis/ADDEDRandomForestClasswithSHAPandother%20visuals.ipynb)
