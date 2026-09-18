# King County Housing EDA

## Client-Centered Analysis of Luxury Waterfront Homes

This project presents an exploratory data analysis of the King County housing market with a client-centered focus.

The client, **Jennifer Montgomery**, is a high-budget buyer looking for a distinctive property in King County. Her priorities include:

- Waterfront location
- High building grade
- Renovated property
- Purchase within approximately one month
- Potential resale within one year

The analysis investigates which property characteristics, locations, and market patterns are most relevant to these requirements.

---

## Client Questions and Hypotheses

### H1 — Waterfront and Building Grade

Do **high-grade waterfront homes** achieve a larger price premium than homes that are either:

- high-grade only, or
- waterfront only?

### H2 — Renovation

Among **older high-grade homes**, do renovated properties achieve higher values than non-renovated properties?

### H3 — Location

Where are high-grade waterfront homes concentrated in King County, and how does their **price per square foot** vary geographically?

Additional client questions:

- How frequently do suitable properties appear in the historical sales data?
- What does the dataset indicate about resale within one year?

---

## Dataset

The analysis is based on the King County housing dataset.

- **21,597 sale records**
- **21,420 unique houses**
- **22 variables**
- Study area: **King County, Washington**

The dataset contains information about:

- Sale date and price
- Bedrooms and bathrooms
- Living and lot area
- Building grade and condition
- Year built and year renovated
- Waterfront and view
- ZIP code
- Latitude and longitude

The raw data files are not included in this repository.

---

## Data Quality and Cleaning

Before analysis, the dataset was investigated for completeness, plausibility, internal consistency, and spatial validity.

Important cleaning and validation decisions included:

- Missing values were preserved as unknown rather than automatically interpreted as zero.
- Renovation years contained a systematic trailing-zero formatting issue and were corrected.
- One implausible record with **33 bedrooms** was identified and the bedroom value was treated as missing rather than guessed.
- Sale dates were converted to datetime format.
- Geographic coordinates were validated for King County.
- Living-area components were checked for internal consistency.

---

## Search Criteria

To translate the client's preferences into measurable variables:

- **High grade:** Grade ≥ 9  
  Approximately 19.7% of sales.

- **Older home:** Built in 1975 or earlier  
  1975 is the median construction year of the unique houses.

- **Renovated:** Renovation year > 0

- **Waterfront:** Waterfront = 1

- **Value metric:**  
  Price per square foot = Sale Price / Living Area

---

## Main Findings

### H1 — High Grade + Waterfront

Median price per square foot:

- High-grade only: **$264/ft²**
- Waterfront only: **$449/ft²**
- High-grade + waterfront: **$573/ft²**

The high-grade waterfront segment showed the strongest observed price premium.

---

### H2 — Renovation

Among older high-grade homes:

- Non-renovated median: **$377.05/ft²**
- Renovated median: **$392.64/ft²**

Renovated properties showed an observed premium of approximately **4.1%**.

---

### H3 — Location

A total of **79 high-grade waterfront homes** were identified.

- Top 4 ZIP codes contain approximately **40.5%** of the target homes.
- Top 6 ZIP codes contain approximately **50.6%**.

Examples of median price per square foot:

- ZIP 98040: approximately **$705/ft²**
- ZIP 98166: approximately **$394/ft²**
- ZIP 98070: approximately **$361/ft²**

The analysis shows substantial geographic variation in the value of high-grade waterfront homes.

---

## Timing

Historical high-grade waterfront sales ranged from:

- **2 to 12 properties per month**
- Average: approximately **6.6 properties per month**

Suitable sales occurred in every observed month.

This represents historical completed-sale activity and should not be interpreted as current listing availability.

---

## Resale Within One Year

The dataset contained:

- **17 high-grade short-term resales**
- **13 of 17** increased in sale price
- Median gross price change: approximately **+2.1%**
- Median holding period: **212 days**

However:

**No waterfront property in the dataset was observed to resell within one year.**

Therefore, the dataset does not provide direct evidence for the one-year resale performance of Jennifer's exact high-grade waterfront target segment.

---

## Client Recommendation

Based on the analysis:

1. Prioritize **high-grade + waterfront** properties.
2. Focus the search on locations where target homes are geographically concentrated.
3. Treat renovation as a useful but secondary criterion.
4. Maintain some flexibility within the one-month purchase window.
5. Do not assume a guaranteed one-year resale return based on this dataset.

---

## Repository Structure

- [`01_assignment.md`](01_assignment.md) — Original project assignment
- [`02_workflow.md`](02_workflow.md) — Recommended EDA workflow
- [`03_fetching_the_data_eda.ipynb`](03_fetching_the_data_eda.ipynb) — Data extraction and database connection
- [`04_eda.ipynb`](04_eda.ipynb) — Data cleaning, exploratory analysis, hypotheses, visualizations, spatial analysis, timing, and resale analysis
- [`column_names.md`](column_names.md) — Dataset column descriptions
- [`pyproject.toml`](pyproject.toml) — Python project dependencies
- [`uv.lock`](uv.lock) — Locked dependency versions

---

## Setup

Clone the repository:

```bash
git clone git@github.com:NooshinHM/king-county-housing-eda-NHM.git

## Tools

The project uses:

- Python
- pandas
- NumPy
- Matplotlib
- PostgreSQL
- DBeaver
- GeoPandas
- Contextily
- PyDeck
- H3

---

## Author

**Nooshin Hadidian M.**

Exploratory Data Analysis Project  
September 2026