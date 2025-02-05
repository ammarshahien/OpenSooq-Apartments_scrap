# OpenSooq Apartments Scraper

This project is a web scraper built in Python that extracts apartment listings from the OpenSooq website for real estate for sale. The scraper collects various details (such as condition, price, features, etc.) for each apartment listing and saves the data into a CSV file.

## Overview

The scraper works by:
- **Fetching Listing URLs:**  
  The `get_html` function retrieves the URLs for individual apartment listings from the search results pages.

- **Extracting Apartment Details:**  
  The `Apartments_data` function scrapes details from each listing page. It dynamically extracts field names and their corresponding values from `<li>` elements and also captures the listing price. Additionally, it stores the URL of each listing for reference.

- **Data Storage:**  
  The scraped data is stored in a CSV file (`Apartments_data.csv`). If the CSV file already exists, new data is appended to it.

## Features

- **Dynamic Field Extraction:**  
  The scraper extracts both standard fields (from `<li>` elements with `<p>` and `<a>`) and multi-line fields (from `<li class="width-100">` elements, using `<p>` and `<p class="width-75">`).

- **Price Extraction:**  
  Price is extracted separately using a dedicated CSS selector.

- **CSV Data Persistence:**  
  The script checks for an existing CSV file and appends new data to avoid data loss.

## Prerequisites

- **Python 3.x**  
- **Required Python packages:**
  - `requests`
  - `beautifulsoup4`
  - `pandas`
  - (Optionally) `lxml` parser for BeautifulSoup

You can install the required packages using pip:

```bash
pip install requests beautifulsoup4 pandas lxml
