# Salt Squared: Walmart Hurricane Sales Analysis

DS2002 Fall 2026 midterm project.
Team: Noor Imat, Angela Benedict, Aubin Barcheck, Nico Roppatte

## What this project is
We analyzed Walmart sales around Hurricane Helene (September 2024) to see which
products surged before the storm, how weather related to sales, and whether the
reported +250% board game spike was real.

## Repo structure
- `Walmart Midterm Submission.ipynb`: final notebook (cleaning, weather join, Q1–Q5, reflections)
- `CHARTER.md`: team charter (roles and responsibilities)
- `data/`
  - `walmart_transactions.csv`: transaction-level sales data
  - `inventory_and_sales.db`: SQLite database (daily sales summary, inventory levels)
  - `store_locations.csv`, `product_catalog.csv`, `distribution_centers.csv`: reference tables
- `notebooks/`: in-class lab and studio notebooks
  - `scratch/`: each member's working notebooks

## How to run it
1. Open `Walmart Midterm Submission.ipynb` in Google Colab.
2. Run all cells (Runtime → Run all). The data loads straight from this repo's GitHub
   links, so nothing needs to be uploaded.
3. Weather data is pulled live from the Open-Meteo Historical Weather API (free, no key).
   Correlation values may shift slightly between runs because of the live API.

## Main findings
- **Q1:** Comparing the 7 days prior to landfall (September 19-25) to a flat baseline week (September 8-15), Breakfast Foods saw the biggest spike in sales, selling 5.16 times their regular sales per day (416% increase), followed by Emergency Supplies at 2.86x (186% increase) which actually sold more overall units (7016 units).
- **Q2:** Fragmented SKUs were hiding just how large Strawberry Pop-Tart sales were during the storm. By consolidating them, we were able to see that the product was a best seller with 4736 units sold in September, and therefore something that should be an inventory focus.
- **Q3:** Sales peaked Sept 24–25, two days before the strongest wind on landfall day
  (Sept 26). The same-day wind correlation was moderate (r = 0.39), but with a 2-day
  lag it was strong (r = 0.82). Customers stocked up ahead of the storm.
- **Q4:** [store-level results]
- **Q5:** The +250% board game spike only happened on one day. Over the full week before
  the storm, entertainment grew +135%, which is less than Breakfast and Emergency Supplies.
  Inventory dropped too (about 128 to 36 units per store), so the demand was real.
  Recommendation: plan for about double normal board game sales, after essentials are stocked.

## Data sources
- Walmart sales and inventory data (provided for the course)
- Open-Meteo Historical Weather API: https://archive-api.open-meteo.com/v1/archive
