# Manufacturing-Line-Performance-Dashboard

- About this project : Personal Project
- Tools : Excel, Power BI

Goal

This project focuses on developing an interactive Power BI dashboard to analyze manufacturing line productivity, track downtime trends, and identify key failure factors. The dashboard provides actionable insights by monitoring MTBF, MTTR, and failure rate, helping stakeholders enhance production efficiency, minimize operational disruptions, and improve equipment reliability for sustained operational performance.

Data

The dataset consists of multiple tables, each capturing different aspects of manufacturing performance. The data was sourced from Maven Analytics Excel dataset and structured into fact and dimension tables to enable efficient analysis. The dataset includes detailed production and downtime records, capturing :
- Line Productivity (Fact Table)
  - Captures batch production details, including efficiency and operator performance.
- Products (Dimension Table)
  - Stores product specifications.
- Line Downtime (Fact Table)
  - Records machine downtime events by batch, including the cause of the issue.
- Downtime Factors (Dimension Table)
  - Categorizes downtime reasons and identifies operator errors.

Process

1. Data Preparation & Transformation

Data Cleaning
- Checked duplicate records and missing values to ensure data integrity.
- Standardized date formats for consistency.

Data Transformation
- Transformed Line Downtime data using Power Query's Unpivot Column function to converted downtime factor columns into a single Factor column and downtime minutes into a single Downtime (mins) column.
- Rename tables for clarity and consistency :
  - Line Productivity → Fact_Line_Productivity
  - Products → Dim_Products
  - Line Downtime → Fact_Line_Downtime
  - Downtime Factors → Dim_Downtime_Factors
- A Dim_Date table was generated to facilitate time-based analysis.

Calculated Columns and Measures

Calculated columns and measures were added to the respective fact tables :
- Fact_Line_Productivity – Includes columns and measures related to batch efficiency, operator performance, and overall line productivity.
- Fact_Line_Downtime – Includes calculations for total downtime, downtime contribution by factor, and operator-related downtime analysis.
- These calculations improve reporting by enabling detailed performance tracking, downtime impact analysis, and efficiency comparisons across batches, operators, and products.

2. Data Modeling

![Image Alt](https://github.com/maryamkamaruddin/Manufacturing-Line-Performance-Dashboard/blob/88c769e6c0bb7887af546d8dfaf3dec1e1478f61/datamodel.jpg)


The data model consists of multiple fact tables, ensuring a clear separation between production efficiency and downtime analysis. The key relationships are :

- Fact_Line_Productivity links to :
  - Dim_Products (via Product)
  - Dim_Date (via Date)
- Fact_Line_Downtime links to :
  - Dim_Downtime_Factors (via Factor)
  - Fact_Line_Productivity (via Batch)
   
Relationships were established between these tables, ensuring smooth filtering and drill-down analysis. The fact tables connect with the dimension tables using one-to-many relationships to ensure efficient querying and effective aggregation.

Design

1. Line Productivity

![Image Alt](https://github.com/maryamkamaruddin/Manufacturing-Line-Performance-Dashboard/blob/88c769e6c0bb7887af546d8dfaf3dec1e1478f61/Manufacturing%20Line%20Performance%20Analysis%20Dashboard-images-0.jpg)

The Line Productivity Dashboard provides stakeholders with key insights into manufacturing performance by tracking batch times, efficiency, and operator performance. This helps :
- Reduces Delays – By pinpointing inefficiencies in batch times.
- Optimizes Resource Allocation – By identifying slowest products and operators.
- Improves Decision-Making – By providing data-driven insights on productivity trends.
- Enhances Workforce Efficiency – By tracking operator performance and training needs.
  
2. Line Downtime

![Image Alt](https://github.com/maryamkamaruddin/Manufacturing-Line-Performance-Dashboard/blob/88c769e6c0bb7887af546d8dfaf3dec1e1478f61/Manufacturing%20Line%20Performance%20Analysis%20Dashboard-images-1.jpg)

The Line Downtime Dashboard provides stakeholders with insights into the factors contributing to production downtime, helping them identify inefficiencies, improve machine reliability, and enhance operator performance. This dashboard can helps :
- Minimizes Production Loss – By addressing top downtime contributors.
- Improves Workforce Efficiency – By identifying operator-related inefficiencies.
- Enhances Machine Reliability – By focusing on recurring failure patterns.
- Optimizes Scheduling & Resource Allocation – By tracking downtime trends and their impact on production.

3. Failure Analysis

![Image Alt](https://github.com/maryamkamaruddin/Manufacturing-Line-Performance-Dashboard/blob/88c769e6c0bb7887af546d8dfaf3dec1e1478f61/Manufacturing%20Line%20Performance%20Analysis%20Dashboard-images-2.jpg)


The Failure Analysis Dashboard focuses on reliability and maintainability through MTBF (Mean Time Between Failure), MTTR (Mean Time To Repair), and Failure Rate (λ). Combined with Fault Tree Analysis, it helps stakeholders understand the root causes of downtime and guides proactive strategies for both maintenance and operator development. This dashboard can help :
- Improve Machine Uptime — By tracking MTBF and aiming for longer failure-free periods.
- Reduce Repair Time — By minimizing MTTR and restoring operations faster.
- Identify Root Causes — Using Fault Tree Analysis to target both human and technical contributors.
- Support Decision-Making — By quantifying failure rates and prioritizing reliability improvements.

Conclusion

The Manufacturing Line Performance Dashboard provides critical insights into productivity and downtime, helping stakeholders optimize operations.
- Line Productivity Analysis identifies inefficiencies in batch times, operator performance, and product efficiency, guiding process improvements.
- Line Downtime Analysis highlights key disruptions like machine failures and operator errors, enabling targeted interventions.
- Failure Analysis uses MTBF, MTTR, Failure Rate, and Fault Tree Analysis to reveal root causes of downtime and balance the focus between human and technical factors for long-term performance stability.

By leveraging these insights, manufacturers can reduce inefficiencies, improve resource allocation, and enhance overall performance, driving continuous improvement and cost savings.


Data source: https://mavenanalytics.io/data-playground 
