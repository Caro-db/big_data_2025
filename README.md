# Project: Market Value Prediction for Football Players

This project aims to build a machine learning model to predict the market value of football players from the top five European leagues based on individual characteristics and performance statistics.

## Workflow Overview

### 1. **Data Collection**
- Scripts are used to **scrape player data** from [Sofascore](https://www.sofascore.com) for each league:
  - `scrape_players_laliga.py`
  - `scrape_players_premierleague.py`
  - `scrape_players_bundesliga.py`
  - `scrape_players_ligue1.py`
  - `scrape_players_serieA.py`

Each script:
- Loads team URLs for its league.
- Collects data for each player: name, age, position, and statistics.
- Saves the data in a CSV file (e.g., `data_laliga.csv`).

### 2. **Market Value Data Collection**
- The `scrape_market_value_transfermarkt.py` script collects the **market value** of players from [Transfermarkt](https://www.transfermarkt.com).
- This data is stored in `data_marketvalue.csv`.

### 3. **Data Integration and Cleaning**
- The `analisis.py` script:
  - Merges the data from all leagues into a unified dataset.
  - Matches players from performance data with market value using both full name and surname.
  - Filters out unmatched or unreliable records.
  - Transforms statistics to a per-90-minute basis.
  - Drops irrelevant features and creates dummy variables.

### 4. **Exploratory Analysis**
- Visualization of market value distributions and log-transformations.
- Correlation heatmaps to understand feature relationships.

### 5. **Model Training and Evaluation**
- Splits the data into training and test sets.
- Fits various machine learning models:
  - Linear Regression
  - Lasso and Ridge Regression
  - Random Forest
  - Gradient Boosting and AdaBoost
- Evaluates model performance using metrics such as RMSE and R^2.

## Outputs
- Cleaned and merged dataset: `data.csv`
- Performance graphs and heatmaps
- Trained regression models for predicting player market value

## Requirements
- Python 3.8+
- Selenium
- BeautifulSoup
- pandas, numpy, matplotlib, seaborn
- scikit-learn
- webdriver-manager

## Notes
- Scraping requires internet connection and may be blocked depending on traffic or anti-bot mechanisms.
- Always run scraping scripts in headless mode to avoid UI issues.
- Ensure paths and ChromeDriver are correctly configured.

---

**Author**: Gaspar Hayduk, Martina Hausvirth, Carolina De Boeck.
**Updated**: March 2025
