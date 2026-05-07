# COVID-19 Economic Impact: Multi-Source Data Integration

## Overview
This project examines the impact of COVID-19 on economic indicators by integrating data from three distinct source types: a CSV flat file (vaccination and case data from Our World in Data), a web-scraped HTML table (GDP by country from MacroTrends), and a REST API (country demographics from the API Ninjas Country API). All three sources are cleaned, transformed, and merged into a unified SQLite database, then queried together for exploratory analysis and visualization.

## Data Sources and Pipeline
| Source Type | Source | Data |
|-------------|--------|------|
| Flat file (CSV) | Our World in Data | COVID cases, deaths, vaccinations, hospitalizations |
| Web scraping (HTML) | MacroTrends | GDP by country |
| REST API | API Ninjas Country API | Population, region, urban population, internet usage, tourism |

## Methods
- **Milestone 2 (Flat File)**: Loaded and cleaned the Our World in Data COVID CSV. Selected relevant columns, handled missing values, standardized data types, and filtered to country-level records
- **Milestone 3 (Web Scraping)**: Parsed a saved HTML page from MacroTrends using BeautifulSoup to extract a GDP table, then cleaned and structured the data for merging
- **Milestone 4 (API)**: Called the API Ninjas Country API for each country in the dataset, retrieved demographic and economic indicators, and converted the JSON responses into a structured DataFrame
- **Milestone 5 (Merging and Visualization)**: Loaded all three cleaned DataFrames into a SQLite database, queried them together with a JOIN across country and year, and produced visualizations exploring relationships between COVID indicators and economic variables

## Repository Contents

**Rename your files to the following before uploading:**

```
covid19-economic-data-integration/
├── 01_flat_file_prep.ipynb          # Milestone 2: cleaning the CSV flat file
├── 02_web_scraping_prep.ipynb       # Milestone 3: scraping and cleaning GDP data
├── 03_api_data_prep.ipynb           # Milestone 4: API call and data cleaning
├── 04_merge_and_visualize.ipynb     # Milestone 5: database merging and analysis
├── milestone1_writeup.docx          # Milestone 1: project proposal and write-up
├── vaccinations_age.csv             # Source: Our World in Data COVID flat file
├── ninja_api_data.csv               # Cached API response data
├── final_transformed_dataset.csv    # Final merged and transformed dataset
├── combined_data.db                 # SQLite database with all three sources joined
└── README.md
```

## Tools
Python, pandas, requests, BeautifulSoup, sqlite3, matplotlib

## How to Run
1. Install dependencies: `pip install pandas requests beautifulsoup4 matplotlib`
2. Run the notebooks in order: `01` through `04`
3. Note that Milestone 3 requires the saved MacroTrends HTML file to be present in the working directory. Milestone 4 requires a valid API Ninjas API key set as a variable in the notebook
