# Insurance-Data-Engineering-Analytics
# Summary
This project explores premium trends across U.S. states, metal tiers, and age groups using the ACA Marketplace Rate PUF datasets (2019–2023).
The goal is to understand how healthcare insurance rates have evolved over time and present clear, interactive insights through a Tableau dashboard.
All data modeling and transformations are handled in Snowflake and dbt, ensuring a scalable, industry-grade analytics workflow.

# Dataset
- ACA Marketplace Public Use Files – Rate PUF (2019–2023)
- Source: CMS Marketplace PUF Data
- Content: Plan-level information including:
           - Premium amounts by metal level and age
           - Issuer identifiers and plan marketing names
           - State and rating area codes
           - Coverage type and family tiers
This dataset allows for year-to-year, tier-to-tier, and state-by-state comparison of premium changes.
# Tech Stack 
1. Snowflake : Cloud data warehouse used to store and query large multi-year ACA datasets efficiently with simple SQL and no setup hassle.
2. dbt (Data Build Tool): Transforms raw data into clean, reliable models—staging to marts—with built-in testing and documentation.
3. Tableau: Connects to Snowflake to build interactive dashboards that highlight premium trends by year, state, and metal tier.

# Workflow 
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/97e18700-f178-485c-a344-cbe6c296bd47" />
