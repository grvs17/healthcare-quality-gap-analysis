# Healthcare Quality Gap Analysis Dashboard

## Project Background

Healthcare quality measurement is critical for patient outcomes and regulatory compliance, yet hospital administrators struggle to identify where to focus improvement efforts across thousands of facilities nationwide. This project analyzes Centers for Medicare & Medicaid Services (CMS) hospital quality data to provide actionable insights for healthcare leaders and policymakers.

The analysis synthesizes performance data across six critical conditions to uncover systemic healthcare delivery gaps and efficiency opportunities.

Insights and recommendations are provided on the following key areas:

- **National Performance Overview:** Assessment of hospital performance distribution across quality measures
- **Geographic Analysis:** Regional patterns in healthcare delivery and quality gaps  
- **Volume-Quality Relationships:** Analysis of case volume adequacy for reliable quality measurement
- **Targeted Improvement Opportunities:** Identification of specific hospitals and regions requiring intervention

**Interactive Dashboard:** [Link to Interactive Dashboard](https://public.tableau.com/shared/QG28JXN2H?:display_count=n&:origin=viz_share_link) - View in Fullscreen Mode

**Technical Documentation:** [Link to SQL queries used for database preparation](Data-Preparation-Methodology.md)

**Dataset Used:** [US Healthcare Readmissions and Mortality](https://www.kaggle.com/datasets/thedevastator/us-healthcare-readmissions-and-mortality)

**Tools Used:** Excel, SQL, Tableau, GitHub, RMarkdown



### Data Structure & Initial Checks

The CMS Hospital Compare dataset consists of hospital-level performance metrics for six critical conditions:
- Acute Myocardial Infarction (AMI) 
- Coronary Artery Bypass Graft (CABG)
- Chronic Obstructive Pulmonary Disease (COPD)
- Stroke
- Heart Failure (HF)
- Pneumonia (PN)

Performance is measured through 30-day mortality and readmission rates, with hospitals categorized as Above, Same, Below, or Too Few Cases to compare against national averages.

Prior to analysis, comprehensive data quality checks were conducted to ensure accuracy and completeness of the performance categorizations.

This dataset consists of **one table** with **columns**: Hospital Name, City, State, ZIP Code,	Measure Name,	Measure ID,	National Average Comparison,	Score,	Lower Estimate,	Higher Estimate,	Measure Start Date, and	Measure End Date. It contains a total of 52,985 **records**.


<img width="1345" alt="Screenshot 2025-05-27 at 1 57 04 PM" src="https://github.com/user-attachments/assets/25b460fb-2c10-484d-961f-59d50525076d" />





## Key Takeaways

The analysis reveals significant systemic inefficiencies in U.S. healthcare delivery. While most hospitals (74.29%) perform at national standards, **21.14% of hospitals lack sufficient case volumes for reliable quality measurement** - representing a critical gap in healthcare infrastructure.

Geographic analysis shows concerning patterns: quality issues cluster in specific regions, and nearly one in four hospitals may be too small to deliver complex care effectively. This presents both patient safety concerns and economic inefficiency opportunities.

Key findings indicate potential for substantial healthcare system optimization through strategic consolidation and referral network development.


## Healthcare System Performance Distribution
<img width="993" alt="Screenshot 2025-05-27 at 12 09 18 PM" src="https://github.com/user-attachments/assets/e8537e3d-a2a0-4347-a3ea-4127dfb07a75" />

- **Quality Measurement Gap:** 21.14% of hospitals nationwide have insufficient case volumes for reliable performance assessment, indicating potential structural inefficiencies in care delivery
- **Performance Standards:** 74.29% of hospitals meet national standards, with only 2.55% performing below benchmarks and 2.03% exceeding them
- **Geographic Disparities:** Eastern Midwest United States shows highest concentration of low-volume hospitals, suggesting regional healthcare infrastructure challenges  
<img width="549" alt="Screenshot 2025-05-27 at 2 18 03 PM" src="https://github.com/user-attachments/assets/f24f474a-7460-4d64-8cd2-b06eadc2a875" />




### Regional Performance Patterns

- **Volume Clustering:** Hospitals with inadequate case volumes concentrate in specific geographic regions, indicating opportunities for care consolidation or specialized referral networks
- **Quality Variations:** Certain conditions like pneumonia show regional performance clustering, with 5% of hospitals underperforming specifically on pneumonia-related metrics
<img width="547" alt="Screenshot 2025-05-27 at 2 23 28 PM" src="https://github.com/user-attachments/assets/273f0376-37cb-48b4-98b0-e34e37838415" />


- **Infrastructure Implications:** The geographic distribution suggests systematic rather than random factors driving performance variations

### Volume-Quality Relationships

- **Scale Efficiency:** The 21% of hospitals with insufficient volumes likely face higher per-case costs and potentially suboptimal patient outcomes
- **Resource Allocation:** Low-volume hospitals may benefit from focusing on primary care while referring complex cases to high-volume centers
- **Network Opportunities:** Regional hub-and-spoke models could address both quality and efficiency concerns

## Recommendations

Based on the analysis, the following strategic recommendations are provided:

- **Healthcare System Consolidation:** With 21% of hospitals lacking adequate case volumes, healthcare systems should evaluate opportunities for procedure consolidation at high-volume centers while maintaining local access for routine care

- **Regional Referral Networks:** Develop formal referral partnerships between low-volume hospitals and specialized centers, particularly in the Eastern Midwest where volume inadequacy clusters

- **Targeted Quality Improvement:** Focus intensive improvement resources on the 2.55% of hospitals performing below standards rather than broad-based initiatives

- **Telemedicine Integration:** Leverage remote consultation capabilities to bring specialist expertise to low-volume hospitals without requiring patient transfer

- **Policy Consideration:** Results suggest potential value in minimum volume standards for complex procedures, with accompanying support systems for affected communities

- **Performance Monitoring Enhancement:** Develop alternative quality metrics for low-volume hospitals to ensure adequate oversight despite limited case numbers

## Caveats and Assumptions

- Outdated information, the dataset only reflects from July 2012 to June 2015 
- Analysis based on CMS-reported data; private pay and uninsured cases are not represented
- Performance categories reflect statistical comparisons to national averages rather than absolute quality thresholds  
- Geographic analysis limited to state-level aggregation; local market dynamics may vary significantly within states
- Volume thresholds for "too few cases" determination follow CMS methodology but may not reflect optimal clinical volumes
- Recommendations assume current regulatory and reimbursement frameworks; policy changes could alter strategic implications
