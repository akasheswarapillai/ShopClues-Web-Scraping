# ShopClues Men's Clothing — Web Scraping & Business Analysis

A beginner-friendly data analytics project that scrapes men's clothing product data from ShopClues, cleans it, explores it, and answers business questions using SQL.

## What this project does

1. **Scrapes** product data from ShopClues using their AJAX endpoint (no browser automation needed).
2. **Cleans** the raw data — prices, discounts, and URLs are converted into usable formats.
3. **Explores** the data to find patterns in price, discount, rating, and shipping.
4. **Analyzes** the data using SQL to answer real business questions.
5. **Summarizes** everything into clear business recommendations.

```
Scraping → Cleaning → EDA → Visualization → SQL → Validation → Business Insights
```

## Why this project is useful

Online store data (prices, discounts, ratings, shipping) can help a business understand:
- How products are priced
- Which products have the strongest promotions
- Which products offer the best value for money
- How shipping and ratings affect customer appeal

## Tools used

| Tool | Purpose |
|---|---|
| `requests` | Send requests to the ShopClues website |
| `BeautifulSoup` | Read and extract data from HTML |
| `pandas` | Store, clean, and analyze the data |
| `re` | Clean numbers out of text (prices, discounts) |
| `matplotlib` | Create simple charts |
| `sqlite3` | Run SQL queries on the cleaned data |

## How the scraping works

- ShopClues loads more products through a background (AJAX) request called `moreProducts`.
- Instead of using a browser tool like Selenium, this project calls that same request directly using `requests`.
- A session is created first (like visiting the page normally) so the requests look natural.
- The scraper pages through results (increasing `page` and `start`) until **400+ unique products** are collected.
- Duplicate products are automatically skipped using their product ID.

## How the data is cleaned

- **Prices**: text like `₹1,299` is converted to the number `1299`.
- **Discounts**: text like `60% Off` is converted to the number `60`.
- **URLs**: links starting with `//` are converted into full `https://` links.
- **Missing values**: if a numeric value (price, discount, rating) is missing, it's filled in with the average of that column, so no products are dropped.

## What the analysis covers

- Cheapest and most expensive products
- Products with the highest discounts
- Free shipping vs. no shipping information
- Price distribution and price spread (histogram and boxplot)
- Rating distribution

### SQL questions answered

- How many products are in the dataset?
- What is the average price?
- Which products are the most expensive?
- Which products are the highest rated?
- How does average price change by rating group?
- Which products have above-average discounts?
- Which products combine a good rating, a strong discount, and a reasonable price ("best value")?

## Key results

- **408 unique products** collected, with no duplicates and no missing names or prices.
- **Average price:** ₹888.85 | **Median price:** ₹899
- **Price range:** ₹159 to ₹1,899
- **Discounts** go as high as 89% on some products.
- **354 of 408 products (about 87%)** offer free shipping.
- Most product cards did not show a rating, so rating-based findings should be treated as directional rather than fully reliable.

## Business takeaways

- Focus pricing and marketing around the ₹159–₹1,899 range, since that's where most products sit.
- Use high-discount products (up to 89% off) to drive flash sales or clearance campaigns.
- Promote free shipping — it already covers the large majority of the catalog.
- Highlight "best value" products (good rating + strong discount + fair price) with badges to catch shopper attention.
- Improve how product ratings are captured on-site, since most items were missing this data.

## Files in this project

| File | Description |
|---|---|
| `ShopClues_project_analysis.ipynb` | The full notebook — scraping, cleaning, analysis, and SQL, in order |
| `shopclues_mens_clothing_400plus.csv` | The cleaned dataset (generated when the notebook runs) |

## How to run it

1. Install the required libraries:
   ```
   pip install requests beautifulsoup4 pandas matplotlib lxml
   ```
2. Open `ShopClues_project_analysis.ipynb` in Jupyter Notebook or JupyterLab.
3. Run the cells from top to bottom.

That's it — the notebook will scrape, clean, analyze, and save the data automatically.
