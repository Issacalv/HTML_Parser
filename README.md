
# Project Title: HTML_Parser

## Description
This Python script extracts links, titles, and domains from multiple HTML files stored in a specified folder. It parses the content of each HTML file, looking for search result links and their corresponding titles, and then captures the domain names of the links. The extracted information is saved into a CSV file, with the option to limit the number of entries.

## Features
- Extracts all hyperlinks (`<a>`) that contain an `<h3>` tag (typically representing search result links).
- Captures the title (`<h3>`) associated with each link.
- Extracts the domain from each link's URL.
- Automatically handles missing data by filling in with "NA" where necessary.
- Option to limit the number of extracted entries.
- Saves the results as a CSV file for easy further processing.

## Usage
1. **Folder Input**: Specify a folder containing the `.html` files to be processed.
2. **CSV Output**: Provide the name of the CSV file where the results will be saved.
3. **Limit**: (Optional) You can specify a limit for the number of entries to extract.

### Example Usage:
```python
extract_links_titles_domains('path/to/html/files', 'output.csv', limit=100)
```

This will parse HTML files in the specified folder, extract up to 100 links, titles, and domains, and save the results in `output.csv`.

## Parameters:
- `parent_folder`: The folder containing the HTML files.
- `output_csv`: The path and name of the CSV file where results will be stored.
- `limit` (optional): The maximum number of entries to extract.

## CSV Output
The script will generate a CSV file with the following columns:
- **Links**: The full URL of the extracted links.
- **Titles**: The text content of the `<h3>` tags associated with the links.
- **Domains**: The domain name extracted from each link.
- **FileName**: The name of the HTML file from which the data was extracted.

## Requirements
- Python 3.x
- Libraries: `beautifulsoup4`, `pandas`, `urllib`, `os`

You can install the required libraries using:
```bash
pip install beautifulsoup4 pandas
```

## How It Works:
1. The script reads all `.html` files from the specified folder.
2. It uses BeautifulSoup to parse the HTML content.
3. For each HTML file:
   - It extracts all links (`<a>` tags) that contain an `<h3>` tag.
   - It retrieves the titles from the `<h3>` tags and the domain names from the links.
4. If a limit is provided, the script stops once the limit is reached.
5. The extracted data is saved into a CSV file with the specified columns.

## Notes:
- The HTML files were saved from web searches to ensure that the sources are preserved in case content is deleted or Google changes search query results.
- This is useful for preserving search results, especially when dealing with frequently updated web content.

## License
This project is licensed under the MIT License – see the LICENSE file for details.
