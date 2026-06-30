# New York Mortgage Lending Analysis

Interactive Power BI dashboard analysing mortgage lending patterns across New York State using federal Home Mortgage Disclosure Act (HMDA) data.

**[Click to view live dashboard](https://app.powerbi.com/view?r=eyJrIjoiOGUyNTRmYzItMzE2Zi00OWNmLWE3YjQtNjMyMGVmOGE2MDQ0IiwidCI6IjVhNzQwY2Q3LTU3NjgtNGQwOS1hZTEzLWY3MDZiMDlmYTIyYyIsImMiOjEwfQ%3D%3D)**

![Dashboard preview](dashboard-preview.png)

> Group project. My contribution: data cleaning, geographic visuals, county-level visuals and DAX normalisation measures

---

## Overview

The Home Mortgage Disclosure Act (HMDA) is a federal law enacted in 1975 requiring lenders to publicly report mortgage application data, enabling analysis of lending patterns and fair-lending compliance across the US.

This project explores **6,052,316 mortgage applications** across **62 New York counties** from **2007–2017**, investigating how lending outcomes vary by geography, time, and income level.

## Research Questions

1. **Temporal:** How have average mortgage loan amounts changed over time, and what was the impact of the 2008 subprime mortgage crisis?
2. **Geographic:** Which NY counties have the highest approval vs. denial rates, and how do loan characteristics vary regionally?
3. **Socioeconomic:** How do interest rates and loan amounts vary across income brackets?

## Data

- **Source:** Home Mortgage Disclosure Act (HMDA) public dataset
- **Coverage:** New York State, 2007–2017
- **Records:** 6,052,316 mortgage applications across 62 counties, mapped to 10 NY OSC Economic Regions (NYC Region, Long Island, Capital District, etc.)
- **Key variables:** loan outcome (originated/denied/withdrawn), loan amount, interest rate spread, applicant income, county

## Methodology

- **Data cleaning:** Filtered incomplete records, handled missing values, standardised county names for geographic mapping
- **Normalisation:** Min-max scaling `(Value − Min) / (Max − Min)` applied to loan amounts so regions with very different price levels (e.g. Manhattan vs. upstate counties) can be compared fairly on a 0–1 scale
- **Correlation analysis:** Income vs. approval rate, loan amount vs. denial rate, rate spread vs. default risk
- **Interactive features:** Loan type / loan purpose filters, toggleable map metric (approval rate, denial rate, normalised average loan amount), time slider (2007–2017)

## Key Findings

- **Approval rates** are highest and most consistent in upstate/rural counties (Tompkins, Monroe, Saratoga ~75–80%), clustering around 70–75% across most of the state
- **Denial rates** are far more geographically concentrated — New York County (Manhattan) stands out with a notably higher denial rate, with Kings, Westchester, and the Bronx also elevated
- **Loan amounts** are highest in Sullivan and Delaware counties and lowest in downstate counties like Kings and Queens, reflecting differences in property values and borrower profiles
- Lending risk (rate spread) varies meaningfully by loan type, with Conventional loans tracking differently from FHA-insured, FSA/RHS-guaranteed, and VA-guaranteed loans over time

## Dashboard Features

- County-level bar chart and choropleth map with switchable metrics (approval rate / denial rate / normalised avg. loan amount)
- Time-series trend of average loan amount and denial rate against economic events
- Lending risk trend by loan type (2007–2017)
- Loan amount density by loan purpose (home purchase, refinancing, home improvement)
- Bubble chart of risk profile over time, with animated year slider

## Tech Stack

Power BI · DAX measures · HMDA public dataset

## Limitations

HMDA data does not include credit scores or debt-to-income ratios, and some small lenders are exempt from reporting. It remains the most comprehensive public dataset available for mortgage lending analysis in the US.
