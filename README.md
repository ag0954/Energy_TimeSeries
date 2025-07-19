# Household Power Consumption Analysis and Prediction

## Authors

Abraham Gutierrez
Robin Shrestha

![Project Banner](figures/gap_analysis_gap_threshold_10.png)

## Overview
This project develops a predictive model to analyze and forecast U.S. household power consumption using 10 years of data (~2M records). By leveraging Python, pandas, and scikit-learn, we created a KNN-based time series model to identify usage patterns, predict future consumption, and provide actionable insights for energy efficiency. The project demonstrates skills in data management, analysis, visualization, and process documentation, aligning with data-driven roles like the Del Monte Foods IT internship.

## Objectives
- **Predict** future household power consumption based on historical data.
- **Identify** key patterns and factors influencing energy usage.
- **Provide** actionable insights to reduce power costs and promote sustainability.

## Key Features
- **Data Preprocessing**: Cleaned dataset, handled 1.25% missing values using linear and spline interpolation, and resampled data for analysis.
- **Gap Analysis**: Identified 71 gaps (56 small, 15 large), with a largest continuous range of 451 days (2007-08-01 to 2008-10-25).
- **Time Series Analysis**: Calculated daily, weekly, and monthly consumption averages; performed seasonal decomposition on `Global_active_power`.
- **Model Development**: Evaluated 7 regression models, with KNN (after hyperparameter tuning) achieving the lowest RMSLE (0.033279).
- **Visualization**: Created Matplotlib plots to communicate trends and insights to stakeholders.

## Repository Structure
- `src/`: Python scripts for data processing, analysis, and modeling (`time_series_analysis.py`).
- `datasets/`: Input data (`electricity_consumption_original.csv`).
- `datasets/results/`: Output CSVs (e.g., `final_interpolated_df.csv`, `gap_summary.csv`).
- `figures/`: Visual outputs (e.g., `gap_analysis_gap_threshold_10.png`, `avg_consumption.png`).
- `docs/`: Project presentation (`ML_Project_Demo_Presentation.pdf`).

## Methodology
1. **Data Cleaning**: Loaded dataset, combined Date/Time into DateTime index, and handled missing values via interpolation.
2. **Gap Analysis**: Identified gaps using a 10-minute threshold, saving results to `gap_summary.csv`.
3. **Interpolation**: Applied linear interpolation for gaps <5 minutes and spline interpolation for 5-10 minute gaps.
4. **Analysis**: Resampled data to daily, weekly, and monthly frequencies; performed seasonal decomposition.
5. **Modeling**: Trained and evaluated 7 regression models, optimizing KNN for best performance.
6. **Visualization**: Generated plots for gap analysis, consumption trends, and model predictions.

![Data Pipeline](figures/data_pipeline_flowchart.png)
*Figure: Data pipeline for preprocessing, analysis, and visualization.*

## Results
- **Data Integrity**: Handled 1.25% missing values, ensuring robust analysis.
- **Largest Continuous Range**: 451 days (2007-08-01 to 2008-10-25).
- **Model Performance**: KNN model achieved RMSLE of 0.033279, outperforming Decision Tree and Gradient Boosting.
- **Insights**: Identified peak consumption periods (e.g., seasonal trends), enabling recommendations for energy-saving strategies.

![Time Series Plot](figures/avg_consumption.png)
*Figure: Daily, weekly, and monthly average consumption trends.*

## Challenges and Solutions
- **Challenge**: Extensive missing data (1.25%) required careful interpolation.
  - **Solution**: Used linear/spline interpolation for small/large gaps.
- **Challenge**: Complex polynomial models underperformed.
  - **Solution**: Optimized KNN with hyperparameter tuning for better accuracy.
- **Challenge**: Computational resource constraints in Deepnote.
  - **Solution**: Streamlined data processing to reduce memory usage.

## Presentation
View the full project presentation for a detailed overview and stakeholder insights: [ML Project Demo Presentation](docs/ML_Project_Demo_Presentation.pdf).

## Skills Demonstrated
- **Technical**: Python, pandas, scikit-learn, Matplotlib, seaborn, SQL (data handling concepts).
- **Data Management**: Cleaning, interpolation, and maintaining data integrity.
- **Data Analysis**: Trend identification and seasonal decomposition.
- **Visualization**: Creating stakeholder-friendly plots for actionable insights.
- **Process Mapping**: Documented data pipeline and analysis workflow.
- **Collaboration**: Worked with a team to design, analyze, and present findings.

## Getting Started
1. Clone the repository:
   ```bash
   git clone https://github.com/ag0954/household-power-time-series.git
