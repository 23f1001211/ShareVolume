# SEC Shares Outstanding Viewer

This single-page web application fetches and displays share outstanding data from the SEC's EDGAR database for publicly traded companies.

## Features

- Fetches share outstanding data directly from SEC's XBRL API
- Processes and displays maximum and minimum share counts
- Supports dynamic company switching via CIK parameter
- Responsive and visually appealing design
- Client-side processing with no server requirements

## Usage

1. Open `index.html` to view data for Church & Dwight (default company)
2. To view data for another company, append `?CIK=XXXXXXXXXX` to the URL where XXXXXXXXXX is a 10-digit CIK number
   - Example: `index.html?CIK=0001018724` for Oracle Corporation

## How It Works

1. Fetches data from SEC's companyconcept API
2. Filters entries with fiscal year > 2020 and valid numeric values
3. Calculates maximum and minimum share counts
4. Displays results with proper formatting

## Requirements

- Modern web browser with JavaScript enabled
- Internet connection for API access

## Files

- `index.html`: Main application file
- `data.json`: Processed data output (for verification)
- `uid.txt`: Unique identifier file
- `LICENSE`: MIT License

## Data Source

Data is fetched from the SEC's EDGAR database via their public XBRL API:

`https://data.sec.gov/api/xbrl/companyconcept/CIKXXXXXXXXXX/dei/EntityCommonStockSharesOutstanding.json`

A proper User-Agent header is included in all requests as per SEC guidelines.

## License

This project is licensed under the MIT License - see the LICENSE file for details.