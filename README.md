# Currency-Exchange-Rate-Scraper

![Chropleth](https://github.com/bkhan1820/Currency-Exchange-Rate-Scraper/blob/main/photos/apps.4865.9007199266244244.8a1b6114-110d-4101-abbc-e2fbbc92cb6a.png)

In this article, I explain how you can scrape daily currency exchange rates from the XE website and saves the data to a CSV file with 2 different methods. The script retrieves exchange rates for a specified range of dates and filters the results to only include rates for a specific currency (in this case, EUR).

In the first method we will use the requests library to make a GET request to the website and retrieve the raw HTML content, and the BeautifulSoup library to parse the HTML and extract the table rows and columns. It then uses a for loop to iterate over the rows and append the data to a Pandas DataFrame. Finally, it selects only the rows with the desired currency code (EUR) and exports them to a CSV file.

## Installation

To run this script, you'll need to have Python 3 and the following Python libraries installed:

- pandas
- requests
- beautifulsoup4

You can install these libraries using pip:

```! pip install pandas requests beautifulsoup4```


## Usage

To use this script, simply run the currency_scraper.py file in your Python environment:

```python currency_scraper.py```

This will retrieve the exchange rates for a default date range (from January 1, 2022 to November 30, 2022) and save the results to a file named exchange_rate_chf.csv.


![Chropleth](https://github.com/bkhan1820/Currency-Exchange-Rate-Scraper/blob/main/photos/Screenshot%202023-02-18%20at%2022.40.31.png)

If you want to specify a different date range or currency code, you can modify the variables in the script accordingly.
