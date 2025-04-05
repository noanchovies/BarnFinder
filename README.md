> [!NOTE]
> Beginner Learning Project focused on web scraping skills and foundational scraping logic




<img src="https://static1.hotcarsimages.com/wordpress/wp-content/uploads/2022/11/302.jpg?q=50&fit=crop&w=420&h=260&dpr=1.5" alt="OLX Image" style="width:15%;"/>

# Second Hand Auto/Moto Scanner for OLX

## Technology Stack

* Python 3.11
* Selenium
* WebDriver Manager
* BeautifulSoup4
* Pandas

## Description

This project is an initial iteration of a Python-based web scraper designed to gather data on used car and motorcycle listings from OLX Portugal (OLX.pt). It leverages modern web scraping techniques t[...]

## Key Features & Approach Highlights

* **Multi-Page Scraping:** Effectively navigates through multiple search result pages using URL parameter manipulation (`?page=N`), demonstrating pagination handling.
* **Efficient Browser Automation:** Utilizes Selenium and WebDriver Manager to control a Chrome instance, crucially reusing a single browser session across multiple page requests for improved efficien[...]
* **Robust Waiting Strategy:** Implements Selenium's `WebDriverWait` to intelligently wait for essential page elements (like the main listing grid) to load, minimizing errors caused by fixed delays an[...]
* **Adaptive Data Extraction:** Employs BeautifulSoup4 with CSS selectors (prioritizing `data-testid` attributes where available, with class-based fallbacks) to parse the rendered HTML and extract key[...]
* **Structured Output:** Organizes scraped data using Pandas DataFrames and saves the results to a CSV file for easy access and further analysis.
* **Forward-Thinking Design:** Includes analysis of OLX.pt's URL structure, identifying parameters for filtering (price, year, fuel type, etc.) and sorting (price, date). This lays the groundwork for [...]

## Challenges & Problem-Solving Showcase

Developing this scraper involved overcoming challenges common to scraping large commercial platforms:

1.  **Initial Tooling/Environment Compatibility:** Early exploration involved evaluating different browser automation tools (like Playwright) within specific server environments on Windows. Encountere[...]
2.  **Dynamic Content & Structure Variations:** OLX.pt required browser automation (Selenium) to ensure all listing content was loaded correctly. Variations in HTML structure between different ad type[...]
3.  **Efficient Pagination:** Dynamically detecting the total number of pages proved unreliable due to how controls were rendered. **Solution:** Adopted a pragmatic approach using a configurable page [...]

## Current Status & Next Steps

* **Status:** Initial working version. Successfully scrapes core data fields from a defined number of pages within the OLX.pt cars category. Saves combined data to CSV.
* **Next Steps:**
    * Implement dynamic URL generation based on user-defined filters and sorting options.
    * Add comprehensive data cleaning and parsing logic (e.g., numeric price, year/km extraction, date parsing).
    * Refine selectors further for edge cases.
    * Integrate database storage for persistent data and tracking changes.
    * Develop logic for more efficient scraping runs (e.g., only fetching newest ads).

## Setup & Usage

1.  Clone the repository.
2.  Navigate into the project directory (`autoscannerpt`).
3.  Create and activate a Python virtual environment (e.g., `python -m venv myenv`, `myenv\Scripts\activate`).
4.  Install dependencies: `pip install -r requirements.txt`
5.  Run the scraper: `python src/autoscannerpt/scraper.py`
    * (Modify configuration constants like `MAX_PAGES_TO_SCRAPE` directly in `src/autoscannerpt/scraper.py` for now).
