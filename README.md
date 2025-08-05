# 🎬 Movie Market Analysis

## 🛠️ Tech Stack

- **Python**
- **Selenium** – For automating browser actions and handling dynamic page scrolling  
- **BeautifulSoup (bs4)** – For HTML parsing and tag extraction  
- **Requests** – For making HTTP requests to movie subpages  
- **LXML** – As the HTML parser  
- **Chrome WebDriver** – For controlling the Chrome browser

---

##  Project Overview

This project performs web scraping on the [Box Office Mojo Showdown Page](https://www.boxofficemojo.com/showdown/) to extract financial data for various movies. The data includes critical insights into each film’s budget, revenue, and other business-related aspects.

The output is a structured dataset suitable for financial analysis, predictive modeling, and industry research.

---

## 🔍 Workflow Overview

1. **Access Main Showdown Page**  
   Using Selenium, the script opens the showdown page in an incognito Chrome browser, scrolls to the bottom to load dynamic content, and saves the entire HTML page locally.

2. **Parse Movie Links**  
   Extracts all movie showdown URLs from the main page using `BeautifulSoup`.

3. **Scrape Each Movie Page**  
   For every movie URL, the script fetches and parses:
   - 🎥 Movie Name
   - 📚 Genre
   - 💸 Production Budget
   - ⭐ MPAA Rating
   - ⏱️ Running Time
   - 🌍 Foreign Gross
   - 🇺🇸 Domestic Gross
   - 📅 Release Date
   - 🛑 Close Date
   - 🏢 Distributor

4. **Data Storage**  
   All data is stored in a structured Python dictionary (`nested_dict`) with one entry per movie.

---

##  Functional Code Breakdown

```python
# Step 1: Open showdown page and scroll to the bottom
driver = webdriver.Chrome()
driver.get("https://www.boxofficemojo.com/showdown/")
# Scroll to load all content
# Save the complete HTML page locally

# Step 2: Parse all <a> tags to get individual showdown links
soup.find_all('a', {'class': 'a-link-normal'}) -> relative URLs
urljoin(base_url, relative_link) -> Full URL

# Step 3: For each movie showdown URL
- Fetch HTML using requests
- Extract data using BeautifulSoup from relevant <td>, <span>, and <a> tags
- Save to nested_dict format
```

## 🎯 Use Cases

- 📊 **Financial analysis of movies**  
  Understand profitability, revenue streams, and spending patterns of various films.

- 📈 **Exploratory Data Analysis (EDA) on budget vs gross performance**  
  Analyze how production budgets correlate with domestic and international gross revenues.

- 🤖 **Predictive modeling on movie success based on features**  
  Build machine learning models to predict movie success using budget, rating, release date, etc.

- 🧩 **Comparative studies between genres, distributors, and time periods**  
  Compare performance across genres (e.g., action vs. drama), studios, or decades.

- 📅 **Trend analysis on release and closure dates**  
  Identify patterns in movie releases, seasonal trends, and theatrical run durations.

