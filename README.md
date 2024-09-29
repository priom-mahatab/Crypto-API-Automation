# CoinMarketCap API Data Retriever

This project retrieves the latest cryptocurrency listings from the CoinMarketCap API and stores the data in a CSV file for further analysis. The script fetches data periodically, making it suitable for tracking cryptocurrency prices over time.

## Features

- Connects to the CoinMarketCap API to fetch the latest cryptocurrency data.
- Allows customization of the number of cryptocurrencies retrieved.
- Saves the data into a CSV file, appending new data each time it runs.
- Implements error handling for connection issues and API rate limits.

## Requirements

- Python 3.x
- Libraries:
  - `requests`
  - `pandas`

You can install the required libraries using pip:

```bash
pip install requests pandas
```

## How to Use
1. Clone this repository to your local machine.
2. Open the Python file in your favorite code editor.
3. Replace the placeholder in the api_runner() function with your desired file path and name where you want to save the CSV file.
```
if not os.path.isfile(r'Enter directory here\File name.csv'):
    df.to_csv(r'Enter directory here\File name.csv', header='column_names')
else:
    df.to_csv(r'Enter directory here\File name.csv', mode='a', header=False)
```
4. Insert your own CoinMarketCap API key in the `headers` dictionary.
```
headers = {
    'Accepts': 'application/json',
    'X-CMC_PRO_API_KEY': 'your_api_key_here',
}
```
5. Run the script. It will execute the API request every minute for 333 iterations, storing the data in the specified CSV file.

## Error Handling
The script includes error handling for connection issues, timeouts, and too many redirects. If an error occurs during the API request, it will print the error message.
