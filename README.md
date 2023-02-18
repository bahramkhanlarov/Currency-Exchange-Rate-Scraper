# Currency-Exchange-Rate-Scraper

![Chropleth](https://github.com/bkhan1820/Currency-Exchange-Rate-Scraper/blob/main/photos/apps.4865.9007199266244244.8a1b6114-110d-4101-abbc-e2fbbc92cb6a.png)

In this article, I explain how you can scrape daily currency exchange rates from the XE website and saves the data to a CSV file with 2 different methods. The script retrieves exchange rates for a specified range of dates and filters the results to only include rates for a specific currency (in this case, EUR).

In the first method the code you provided is an example of web scraping, as it retrieves data from a website (in this case, https://www.xe.com/currencytables/) and extracts the relevant information from the HTML content. The pd.read_html() function used in the code is specifically designed for parsing HTML tables, which is a common technique used in web scraping. By iterating over a range of dates, the script is able to scrape data from the website for each day in the specified range, and save the results in a structured format for further analysis.


## Requirements

This script requires Python 3 and the following packages:

- pandas
- datetime

You can install these libraries using pip:

```! pip install pandas datetime ```


## Usage

To use this script, simply run the currency_scraper.py file in your Python environment:

```python exchange_rate_scraper.py ```

This will retrieve the exchange rates for a default date range (from January 1, 2022 to November 30, 2022) and save the results to a file named exchange_rate_chf.csv.


![Chropleth](https://github.com/bkhan1820/Currency-Exchange-Rate-Scraper/blob/main/photos/Screenshot%202023-02-18%20at%2022.40.31.png)

If you want to specify a different date range or currency code, you can modify the variables in the script accordingly.

## Code explanation

Import the pandas library and the datetime module, which provides classes for working with dates and times.

```import pandas as pd
import datetime```

## License

This project is licensed under the MIT License. Feel free to use and modify this script as you see fit.
