# Quantium Task 1 – Retail Customer Analytics

This project analyzes Quantium transaction and customer purchase behaviour data to uncover sales trends, customer segment performance, and product preferences. The notebook focuses on data cleaning, feature engineering, customer segmentation, statistical testing, and actionable commercial insights.

## Project Objective

The goal of this analysis is to:

- examine transaction and customer datasets for quality issues and business patterns
- identify the customer segments driving chip sales
- engineer useful product features such as pack size and brand
- compare purchasing behaviour across customer segments
- generate evidence-based recommendations for strategy

## Dataset Overview

The analysis uses two datasets:

- `QVI_transaction_data.xlsx` – transactional sales data
- `QVI_purchase_behaviour.csv` – customer demographic and behavioural data

### Transaction data includes:
- transaction date
- store number
- loyalty card number
- transaction ID
- product number
- product name
- product quantity
- total sales

### Customer data includes:
- loyalty card number
- lifestage
- premium customer category

## Key Tasks Completed

### 1. Data Loading and Inspection
- loaded transaction and customer datasets into pandas
- checked column types and previewed the data
- converted Excel serial dates into proper datetime format

### 2. Data Cleaning
- removed non-chip products such as salsa items
- identified and removed a commercial outlier customer (`LYLTY_CARD_NBR = 226000`)
- verified missing dates and sales gaps across the analysis period

### 3. Exploratory Data Analysis
- analyzed transaction volume over time
- observed a sales increase leading up to Christmas
- confirmed zero sales on Christmas Day, likely due to store closures
- reviewed quantity and sales distributions for unusual behaviour

### 4. Feature Engineering
- extracted `PACK_SIZE` from product names
- extracted and standardized `BRAND` names from product descriptions
- corrected inconsistent brand labels such as:
  - `DORITO` → `DORITOS`
  - `SMITH` → `SMITHS`
  - `INFZNS` → `INFUZIONS`
  - `WW` → `WOOLWORTHS`

### 5. Customer Analysis
- explored customer composition by `LIFESTAGE`
- explored customer composition by `PREMIUM_CUSTOMER`
- merged customer and transaction datasets for segment analysis

### 6. Segment Performance Analysis
The notebook evaluates:

- total sales by customer segment
- number of customers per segment
- average units purchased per customer
- average price per unit by segment

### 7. Statistical Testing
A t-test was performed to compare average unit prices between:

- Mainstream young and midage singles/couples
- Budget and premium young and midage singles/couples

This test showed that mainstream young and midage singles/couples pay a significantly higher price per unit.

### 8. Deep Dive: Mainstream Young Singles/Couples
This segment was analyzed further to identify:

- brand affinity relative to the rest of the population
- pack size affinity relative to the rest of the population
- likely preference patterns driving higher spend

## Main Insights

### Top revenue-driving segments
- Budget – Older Families
- Mainstream – Young Singles/Couples
- Mainstream – Retirees

### Behavioural findings
- Mainstream young singles/couples and retirees contribute strongly to sales because they represent a large share of customers
- older families and young families tend to buy more units per customer
- mainstream young and midage singles/couples are willing to pay more per pack than their budget and premium counterparts

### Brand insights
Mainstream young singles/couples over-index on:
- Tyrrells
- Twisties
- Kettle
- Doritos
- Tostitos
- Pringles

They under-index on products like Burger Rings.

### Pack size insights
Mainstream young singles/couples show stronger preference for larger pack sizes such as:
- 270g
- 330g
- 380g

A closer inspection showed that the 270g preference is heavily linked to Twisties products.

## Business Recommendation

Based on the analysis, Quantium should focus on **Mainstream Young Singles/Couples** as a high-value target segment.

Recommended actions:

- position premium and trend-driven chip brands toward this segment
- prioritize brands such as Tyrrells, Kettle, Twisties, Doritos, and Pringles in promotions
- use impulse-oriented marketing and merchandising strategies
- consider pack-size strategy carefully, especially for large-format snack products
- continue supporting strong-volume family segments with value-focused offers

## Visualizations Included

The notebook includes charts and heatmaps such as:

- transaction trends over time
- December transaction trend zoom-in
- pack size histogram
- sales heatmap by lifestage and premium status
- customer count heatmap by segment
- average units purchased by segment
- average price per unit by segment
- brand affinity chart
- pack size affinity chart

## Tools and Libraries Used

- Python
- pandas
- numpy
- matplotlib
- seaborn
- scipy
- Jupyter Notebook / Google Colab

## Project Structure

```bash
.
├── quantium_task1.ipynb
├── QVI_transaction_data.xlsx
├── QVI_purchase_behaviour.csv
└── README.md
```

## How to Run

1. Clone this repository:

```bash
git clone https://github.com/your-username/your-repo-name.git
cd your-repo-name
```

2. Install dependencies:

```bash
pip install pandas numpy matplotlib seaborn scipy openpyxl
```

3. Open the notebook:

```bash
jupyter notebook
```

4. Update dataset file paths if necessary, especially if you are not using Google Colab.

## Notes

- The original notebook was written in Google Colab and mounts Google Drive for data access.
- If running locally, replace the Google Drive path logic with local file paths.
- Dataset files may need to be added manually if they are not included in the repository.

## Future Improvements

- convert the notebook into a cleaner end-to-end analysis pipeline
- separate data cleaning, feature engineering, and visualization into reusable scripts
- add a final presentation dashboard or report
- make file handling environment-independent instead of relying on Google Drive

## Author

Reatile Setilo
