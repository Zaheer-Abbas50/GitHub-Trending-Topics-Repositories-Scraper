# GitHub Trending Topics & Repositories Scraper

This project scrapes trending topics from the GitHub Topics page (https://github.com/topics) and then extracts information about the top repositories for each topic.

## Overview

The project performs the following steps:

1.  **Scrapes GitHub Topics Page:** Downloads the main GitHub Topics page using the `requests` library.
2.  **Parses Topics:** Uses `BeautifulSoup4` to parse the HTML and extract the names, descriptions, and URLs for trending topics.
3.  **Saves Topics Data:** Stores the extracted topic information into a CSV file (`Topics info.csv`).
4.  **Scrapes Top Repositories:** For each topic page URL, it downloads the page.
5.  **Parses Repositories:** Uses `BeautifulSoup4` to parse the HTML of each topic page and extract details for the top repositories listed (typically username, repository name, URL, and star count).
6.  **Saves Repositories Data:** Stores the extracted repository information for each topic into separate CSV files (e.g., `3DTopicno1.csv`, `AjaxTopicno2.csv`, etc.).

## Technologies Used

*   **Language:** Python (within a Jupyter Notebook `GitHubWebScrapingProject.ipynb`)
*   **Libraries:**
    *   `requests`: For making HTTP requests to download web pages.
    *   `beautifulsoup4`: For parsing HTML content.
    *   `pandas`: For creating and managing dataframes and saving data to CSV files.

## Files in this Repository

*   `GitHubWebScrapingProject.ipynb`: The main Jupyter Notebook containing the Python code for scraping.
*   `Topics info.csv`: A CSV file containing the list of scraped topics, their descriptions, and URLs.
*   `[TopicName]Topicno[Number].csv` (Multiple files): CSV files containing the top repositories for each scraped topic (e.g., `3DTopicno1.csv`, `AjaxTopicno2.csv`). *(Consider placing these in a subfolder like `topic_repositories/` for better organization)*

## How to Run

1.  **Prerequisites:**
    *   Python 3 installed.
    *   Jupyter Notebook or JupyterLab installed (`pip install notebook` or `pip install jupyterlab`).
2.  **Clone the repository:**
    ```bash
    # Example using the suggested name:
    git clone https://github.com/Zaheer-Abbas50/github-topic-scraper.git
    cd github-topic-scraper
    ```
3.  **Install required libraries:**
    ```bash
    pip install requests beautifulsoup4 pandas notebook
    ```
4.  **Run Jupyter Notebook:**
    ```bash
    jupyter notebook GitHubWebScrapingProject.ipynb
    ```
5.  Open the notebook in your browser and run the cells sequentially. The script will scrape the data and generate/overwrite the CSV files in the repository directory.

## Notes

*   Web scraping relies on the structure of the target website (GitHub Topics). If GitHub changes its page layout, the scraper might break and require updates.
*   Be mindful of GitHub's terms of service and robots.txt file regarding scraping. Avoid sending too many requests in a short period.

