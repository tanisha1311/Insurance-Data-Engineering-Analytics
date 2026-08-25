# Insurance-Data-Engineering-Analytics
## Summary
This project explores premium trends across U.S. states, metal tiers, and age groups using the ACA Marketplace Rate PUF datasets (2019–2023).
The goal is to understand how healthcare insurance rates have evolved over time and present clear, interactive insights through a Tableau dashboard.
All data modeling and transformations are handled in Snowflake and dbt, ensuring a scalable, industry-grade analytics workflow.

## Dataset
- ACA Marketplace Public Use Files – Rate PUF (2019–2023)
- Source: CMS Marketplace PUF Data
- Content: Plan-level information including:
           - Premium amounts by metal level and age
           - Issuer identifiers and plan marketing names
           - State and rating area codes
           - Coverage type and family tiers
This dataset allows for year-to-year, tier-to-tier, and state-by-state comparison of premium changes.
## Tech Stack 
1. Snowflake : Cloud data warehouse used to store and query large multi-year ACA datasets efficiently with simple SQL and no setup hassle.
2. dbt (Data Build Tool): Transforms raw data into clean, reliable models—staging to marts—with built-in testing and documentation.
3. Tableau: Connects to Snowflake to build interactive dashboards that highlight premium trends by year, state, and metal tier.

## Workflow 
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/97e18700-f178-485c-a344-cbe6c296bd47" />

Raw ACA plan_attributes and rate_pufs CSVs (2021–2025) are loaded into Snowflake as-is. dbt staging models clean and standardize each dataset separately, then combine all five years into single staging models per dataset. A mart model joins the two datasets together, and a dedicated dashboard mart trims this down to only the fields needed for Tableau, keeping the reporting layer clean and query-ready.

## Dashboard
<img width="1372" height="874" alt="image" src="https://github.com/user-attachments/assets/1098c01c-d4e5-4c42-9f75-155564dd06d0" />
[(https://public.tableau.com/app/profile/tanisha.singh1274/viz/InsurancePremiumAnalysis_17781119694850/MarketOverview)]

## Key Findings

- The dataset spans 2021–2025 and covers over 1 million plan records across all 50 states, drawn from CMS's ACA Marketplace Rate PUF files
- Average premium across all years and plans sits at $504.33, with year-over-year premium growth of approximately 5.2%
- Platinum plans consistently had the highest premiums across all five years, rising from roughly $1,000 in 2021 to over $1,500 by 2025, with the steepest increase occurring after 2023
- Premiums scale strongly with age — the oldest age band (61+) pays about 3.8x more than the youngest band (0-14), with a fairly steady increase across each age group in between
- Florida leads all states by a wide margin in plan/issuer volume, well ahead of the next-highest states (Texas, Ohio)

## Project Structure

<img width="1010" height="746" alt="image" src="https://github.com/user-attachments/assets/d229f624-4fbd-4ef4-b595-d056f39e98fe" />
