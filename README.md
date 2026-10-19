# 📚 The Bookstore Intelligence Mission

An automated web scraping, data analytics, and inventory optimization pipeline designed to extract market intelligence from an e-commerce competitor catalogue ([Books to Scrape](https://books.toscrape.com/)).

---

## 📌 Project Overview
This project was developed for the **Business Analytics & Data Management** assignment at **National University of Computer & Emerging Sciences (FAST-NUCES)**. 

The objective is to act as part of a Market Intelligence Team for an online bookstore. Since competitors do not publish raw datasets, an automated pipeline was constructed to scrape, clean, and analyze competitor catalogue data to drive strategic inventory decisions and solve a £100 budget optimization problem.

---

## 🛠️ Tech Stack & Libraries
- **Language:** Python 3.x (Google Colab / Jupyter Notebook)
- **Web Scraping:** `requests`, `BeautifulSoup` (`bs4`)
- **Data Manipulation & Analytics:** `pandas`, `NumPy`
- **Visualization:** `matplotlib`

---

## ⚙️ Key Technical Features

1. **Automated & Scalable Web Scraper:**
   - Robust pagination engine handling multi-page navigation across all 50 catalogue pages (1,000 product records).
   - Handles dynamic 404 response detection for automatic loop termination.
   - Enforces UTF-8 encoding and polite scraping practices (session reuse & delay headers).

2. **Data Pipeline & Normalization:**
   - Extracts title, price, star rating, stock availability, and relative product URLs.
   - Maps textual star ratings (`One` to `Five`) into numerical integers (`1` to `5`).
   - Cleans currency strings into standard floating-point values.
   - Automatically exports sanitized dataset to `competitor_books.csv`.

3. **Algorithm Design (£100 Knapsack Challenge):**
   - Implements a **$0/1$ Knapsack algorithm via Dynamic Programming** using exact integer pence conversions.
   - Optimizes book selection to maximize total cumulative star rating without exceeding a £100 budget constraint.

---

## 📊 Key Insights & Business Recommendations

- **Catalogue Metrics:** 1,000 titles analyzed with an average price of **£35.07** (ranging from £10.00 to £59.99).
- **Quality Distribution:** High-rated 5-star books represent a scarce segment (**19.6%** / 196 books).
- **Price-Quality Independence:** No correlation exists between price and star rating (e.g., the overall cheapest book at £10.00 holds a 5-star rating).
- **Optimization Strategy:** Under the £100 constraint, the dynamic programming solver allocated **£98.68** across **9 titles** (8 of which are 5-star rated), securing a maximum rating score of **44**.

---

## 📁 Repository Structure

```text
├── Bookstore_Intelligence.ipynb   # Interactive Jupyter / Google Colab Notebook
├── bookstore_scraper.py           # Standalone Python scraping script
├── competitor_books.csv           # Complete dataset of 1,000 scraped records
├── rating_counts.png              # Generated bar chart of star rating counts
├── Assignment_Report.pdf          # Full technical assignment report
└── README.md                      # Project documentation
