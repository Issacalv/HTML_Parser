
# HTML Data Extraction Tool

This tool is designed to extract links, titles, and domain names from HTML files and export them into an Excel file. It also includes functionality to compare two sets of links and find new or unique entries.

## Features
- **Extract Data from HTML Files**: 
  - Extracts links from HTML files that have associated titles (`<h3>` elements).
  - Retrieves domain names from the links and organizes them in an Excel file.
  - Handles multiple HTML files with a customizable limit on the number of entries.
  - Uses **natural sorting** for filenames with numeric components, treating filenames without numbers as if they have an implied "1".

## Usage
1. **Extract Data**: Call the `extract_data()` function with the folder path containing HTML files and specify the desired output file name.
   ```python
   extract_data("/path/to/html/files", "output_file")
   ```
   - Parameters:
     - `folder`: The folder containing the HTML files.
     - `output_file`: The base name for the output Excel file (the folder name will be appended).
     - `limit`: (Optional) Maximum number of entries to extract.

2. **Compare Links**: Use the `compare_links()` function to find new links by comparing two sets of extracted links.
   ```python
   compare_links(all_links_parent, all_links_new, viewLinks=True, export=True, export_name="new_links.xlsx")
   ```
   - Parameters:
     - `all_links_parent`: The original set of links.
     - `all_links_new`: The new set of links to compare.
     - `viewLinks`: (Optional) Print new links to the console (default: False).
     - `export`: (Optional) Export the new links to a file (default: False).
     - `export_name`: The output file name for exporting new links (supports .txt or .xlsx).

## Requirements
- Python 3.x
- BeautifulSoup (`bs4`)
- Pandas
- urllib
