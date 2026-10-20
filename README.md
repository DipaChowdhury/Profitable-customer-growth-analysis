# Profitable-customer-growth-analysis
An end-to-end customer analytics project using Python and Tableau to analyze revenue, retention, and customer segments.
This project analyzes historical transactions from a UK online retailer
to identify customer-retention opportunities, understand revenue
concentration, and support evidence-based marketing decisions.
Project overview
Retailers need to understand not only how much revenue they generate,
but also which customers return, which valuable customers may be
lapsing, and where retention efforts could have the greatest impact.

This project uses transaction-level retail data to answer:
- How much revenue and how many orders are represented in the cleaned
  dataset?
- How much revenue comes from repeat customers?
- Which customer segments contribute the most revenue?
- Which high-value customers may warrant a win-back campaign?
- How does revenue change over time?
- Which retention actions should the business test first?
Tools used
- Python for data cleaning and analysis
- Pandas and NumPy for data processing and calculations
- Tableau Public for interactive visualization
- Jupyter Notebook for running and checking the analysis
Key findings
The analysis covers transactions from 1 December 2009 to 9 December
2011. After cleaning, the dataset contained 776,844 transaction
rows, representing 5,853 identifiable customers and 36,600
orders.

  Metric                                        Result
  Total revenue                            £17,081,129
  Identifiable customers                         5,853
  Orders                                        36,600
  Average order value                          £466.70
  Revenue per identifiable customer          £2,918.35
  Adjusted 90-day repeat purchase rate           44.2%
  Revenue from repeat orders                     85.0%
Customer segment findings
  Segment                    Customers       Revenue   Share of revenue
  Champions                        967   £11,699,888              68.5%
  High-value at risk               204    £1,481,889               8.7%
  Active repeat buyers           1,546    £1,946,323              11.4%
  Recent one-time buyers           372      £130,362               0.8%
  Lapsed repeat buyers           1,474    £1,428,746               8.4%
  Lost one-time buyers           1,290      £393,921               2.3%
What the findings suggest
- Protect high-value relationships: Champions account for the
  largest share of observed revenue, so retention and customer-service
  quality are important.
- Investigate high-value customers at risk: The 204 customers in
  this segment represent a potential win-back opportunity.
- Encourage a second purchase: Recent one-time buyers may be
  suitable for a targeted second-purchase journey.
- Use proportionate win-back spending: Test lower-cost automated
  messages for lapsed customers before committing to expensive
  campaigns.
These are recommendations based on historical patterns, not proof that a
campaign will cause revenue to increase. Any campaign should be tested
and measured.
Data source
The project uses the UCI Online Retail II dataset, which contains
invoice-level transactions from a UK-based online retailer.
- Dataset page:
  https://archive.ics.uci.edu/dataset/502/online+retail+ii
- Period analyzed: 1 December 2009 -- 9 December 2011
- Currency: GBP (£)
The original Excel dataset is not included in this repository. Download
it from the official source if you want to rerun the analysis.
Data cleaning
The pipeline applies the following cleaning steps:
1. Remove rows with missing or invalid customer IDs.
2. Exclude cancellation invoices (invoice numbers beginning with C).
3. Remove transactions with non-positive quantity or price.
4. Exclude non-product codes such as postage, fees, and adjustments.
5. Remove exact duplicate rows.
6. Derive order-level, customer-level, cohort, and segment summaries
   for analysis.
The cleaning process reduced the dataset from 1,067,371 raw rows to
776,844 rows. Because guest checkouts are excluded, customer metrics
describe identifiable customers rather than every transaction in the raw
data.
Dashboard
The Tableau Public dashboard includes:
- KPI views for revenue, customers, and repeat purchase rate
- Monthly revenue trend
- Revenue contribution by customer segment
- A summary of key business insights
Open the dashboard: Profitable Customer Growth
Analysis
Data interpretation note: The dataset ends on 9 December 2011, so
December 2011 is a partial month and should not be compared with
complete months without qualification.

How to run the Python analysis
1. Download the data
Download Online Retail II from the UCI dataset page linked above. Keep
the Excel file locally; do not commit the raw data to this repository.
2. Install dependencies
Create and activate a virtual environment if desired, then install the
packages used by the script:
python -m venv .venv
source .venv/bin/activate
# On Windows: .venv\Scripts\activate
pip install pandas numpy openpyxl
3. Run the script

Limitations
- Historical, observational data: Associations do not establish
  causation. Retention recommendations need controlled tests.
- Customer identification: Transactions without a valid customer
  ID were excluded from customer-level analysis.
- Wholesale effects: Some customers may purchase in large
  quantities, so revenue and order metrics may reflect
  business/wholesale purchasing patterns.
- No observed marketing costs or product costs: The dataset does
  not provide actual advertising spend or product cost. Customer
  acquisition cost (CAC), profit, and return on marketing spend cannot
  be directly calculated from these transactions alone. Any CAC
  ceiling based on an assumed margin or target ratio is a scenario,
  not a measured result.
- Partial final month: December 2011 contains data only through 9
  December.
- Segment snapshot: Customer segments are based on activity at the
  end of the observed period and should not be interpreted as a
  time-varying segment history.
