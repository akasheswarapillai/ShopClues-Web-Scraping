# ShopClues Men's Clothing Web Scraping & Data Analysis

A Python-based web scraping and data analysis project that collects publicly accessible product data from the **ShopClues Men's Clothing** section using Selenium.

The scraped data is cleaned, transformed, analyzed, and visualized to identify useful product, pricing, discount, rating, review, and brand insights.

## 📌 Project Overview

This project demonstrates a complete **Data Analyst workflow**:

**Web Scraping → ETL → Data Cleaning → Feature Engineering → EDA → Data Visualization → SQL Analysis → Business Insights**

## 🎯 Objectives

* Scrape Men's Clothing product data using Selenium
* Collect around 300+ unique product records
* Handle dynamically loaded products
* Clean and transform raw web data
* Handle missing and duplicate values
* Perform exploratory data analysis
* Create meaningful visualizations
* Perform SQL-based analysis
* Generate business insights from the dataset

## 🛠️ Technologies Used

* **Python**
* **Selenium**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Seaborn**
* **SQLite / SQL**
* **Jupyter Notebook**

## 📊 Data Collected

The project attempts to collect:

* Product Name
* Product URL
* Category
* Subcategory
* Brand
* Original Price
* Selling Price
* Discount
* Rating
* Review Count
* Availability
* Seller Name

## 🔄 ETL Process

### Extract

Product information is collected from the ShopClues Men's Clothing webpage using Selenium WebDriver.

### Transform

The raw data is processed using Pandas:

* Remove duplicate products
* Clean product names
* Convert prices into numeric values
* Convert discounts into percentages
* Convert ratings into numeric values
* Clean review counts
* Handle missing values
* Create derived features

### Load

The cleaned dataset is stored as a CSV file and loaded into SQLite for SQL analysis.

## 📈 Feature Engineering

Additional features are created to improve analysis:

* `discount_amount`
* `calculated_discount_pct`
* `price_category`
* `rating_category`
* `review_category`

## 📊 Exploratory Data Analysis

The project analyzes:

* Product and brand distribution
* Average and median selling price
* Highest-priced products
* Highest-discounted products
* Most-reviewed products
* Highest-rated products
* Brand performance
* Price and rating relationships
* Discount and review relationships

## 📉 Data Visualization

Visualizations are created using Matplotlib and Seaborn, including:

* Product count by brand
* Selling price distribution
* Rating distribution
* Discount distribution
* Top expensive products
* Top discounted products
* Top reviewed products
* Price vs Rating
* Discount vs Review Count

## 🗄️ SQL Analysis

SQLite is used to perform analytical queries such as:

* Top 10 expensive products
* Top 10 discounted products
* Brand-wise product count
* Brand-wise average rating
* Products with rating above 4
* Products with discount above 50%
* Top reviewed products

## 📁 Project Structure

```text
ShopClues-Web-Scraping/
│
├── ShopClues_Mens_Clothing_Selenium_ETL_700_FIXED.ipynb
├── shopclues_mens_clothing_raw.csv
├── shopclues_mens_clothing_final.csv
├── shopclues_mens_clothing_quality_report.csv
└── README.md
```

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone <your-repository-url>
cd ShopClues-Web-Scraping
```

### 2. Install required libraries

```bash
pip install selenium pandas numpy matplotlib seaborn
```

### 3. Open the notebook

```bash
jupyter notebook
```

Run the notebook cells sequentially.

## ⚠️ Important

The website structure may change over time. Selenium selectors and scraping logic may need to be updated if ShopClues changes its webpage structure.

This project does not attempt to bypass CAPTCHA, authentication, Cloudflare, robots.txt, rate limits, or other anti-bot/access restrictions.

## 👨‍💻 Skills Demonstrated

**Web Scraping | Python | Selenium | ETL | Data Cleaning | Pandas | NumPy | SQL | SQLite | EDA | Data Visualization | Business Analysis**
