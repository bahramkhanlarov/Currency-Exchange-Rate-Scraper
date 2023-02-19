# Currency-Exchange-Rate-Scraper

![Chropleth](https://github.com/bkhan1820/Currency-Exchange-Rate-Scraper/blob/main/photos/apps.4865.9007199266244244.8a1b6114-110d-4101-abbc-e2fbbc92cb6a.png)

In this article, I explain how you can scrape daily currency exchange rates from the XE website and saves the data to a CSV file. The script retrieves exchange rates for a specified range of dates and filters the results to only include rates for a specific currency (in this case, EUR).

The provided code is an example of web scraping, as it retrieves data from a website (in this case, https://www.xe.com/currencytables/) and extracts the relevant information from the HTML content. The pd.read_html() function used in the code is specifically designed for parsing HTML tables, which is a common technique used in web scraping. By iterating over a range of dates, the script is able to scrape data from the website for each day in the specified range, and save the results in a structured format for further analysis.


## Requirements

This script requires Python 3 and the following packages:

- pandas
- datetime

You can install these libraries using pip:

```! pip install pandas datetime ```


## Usage

To use this script, simply run the currency_scraper.py file in your Python environment:

```python exchange_rate_scraper.py ```

This will retrieve the exchange rates for a default date range (from January 1, 2022 to February 18, 2023) and save the results to a file named exchange_rate_chf.csv.


![Chropleth](https://github.com/bkhan1820/Currency-Exchange-Rate-Scraper/blob/main/photos/Screenshot%202023-02-18%20at%2022.40.31.png)

If you want to specify a different date range or currency code, you can modify the variables in the script accordingly.

## Code explanation

1. Import the pandas library and the datetime module, which provides classes for working with dates and times.

```
import pandas as pd
import datetime
```

2. Import the timedelta and date classes from the datetime module. These classes will be used to generate a range of dates between a start date and an end date.

````
from datetime import timedelta, date
````

3. Define a function called daterange that takes a start date and an end date as arguments and yields a sequence of dates between the two. The function uses the timedelta and range functions to generate the sequence of dates.

```
def daterange(start_date, end_date):
    for n in range(int ((end_date - start_date).days)):
        yield start_date + timedelta(n)
````

4. Set the starting and ending dates for the period for which exchange rates will be scraped.

````
start_date = date(2022, 1, 1)
end_date = date(2023, 2, 18)
````

5. Create an empty pandas DataFrame to store the exchange rate data.

````
df = pd.DataFrame()
````
6. Iterate over each date in the date range and scrape the exchange rate data for that date using the pd.read_html function. The function takes a URL as an argument, which is generated using the date and a base URL. The function returns a list of tables, and we select the first table in the list using [0]. We add a new column to the DataFrame called 'Date', which contains the date of the exchange rate data.

`````
for single_date in daterange(start_date, end_date):
    dfs = pd.read_html(f'https://www.xe.com/currencytables/?from=CHF&date={single_date.strftime("%Y-%m-%d")}')[0]
    dfs['Date'] = single_date.strftime("%Y-%m-%d")
    df = df.append(dfs)
`````

7. Define the column names for the DataFrame

````
columns = ['Currency code', 'Currency name', 'Units per CHF', 'CHF per Unit', 'Date']
`````

8. Select only the rows of the DataFrame where the currency is EUR, and save the resulting DataFrame to a CSV file called 'exchange_rate_chf.csv'.

 `````
df_chf = df.loc[df['Currency'] == 'EUR']
df_chf.to_csv('exchange_rate_chf.csv')
`````

## Practical use cases:

Some practical use cases specifically for exchange data for CHF-Euro:

Financial modeling: The exchange rate data can be used in financial models to forecast the future exchange rates between Euro and CHF. This can be useful for businesses that have cross-border transactions between the two currencies.

International trade: If you are a business owner who imports or exports goods from or to Switzerland or the European Union, the exchange rate data can help you determine the best time to make a transaction and can inform your purchasing and selling decisions.

Portfolio diversification: Investors who want to diversify their portfolio with foreign currency assets can use the exchange rate data to decide the best time to buy or sell Euro or CHF.

Accounting and tax reporting: Companies with international operations may need to use the exchange rate data to convert their financial statements and tax reporting from Euro to CHF or vice versa.

Travel planning: Individuals who are planning to travel from a Eurozone country to Switzerland can use the exchange rate data to determine the current exchange rate and how much they should budget for their trip.

I hope this helps!

## License

This project is licensed under the MIT License. Feel free to use and modify this script as you see fit.
