# processing-python-web-scraped-data
This project is split between creating a Python web-scraper to scrape the web for info on ML-related websites, processing the web-scraped data, and finally tokenizing it to make it ML model ready.

# Python web-scraper
The purpose of this Python web scraper is to scrape websites for relevant information and store said info in a CSV file. The info I chose to be scraped is 'Title', 'Description', 'URL', 'Number of Words', and 'Keywords' and The 'BeautifulSoup' library was used to assist in web-scraping. The model first scrapes a decided seed of inputs and actively adds websites found within the scraped websites back into the seed. This process ensures scraping as many websites as possible. 
The raw scraped data is to be found in the "Python-web-scraping" folder alongside the code to the scraper.

# pre-processing
During the process of pre-processing the data:
- Columns with failed scrapings were dropped ['403 Forbidden', 'Just a moment...]
- The "Number of Words" column was checked to ensure that the column didn't contain any non-numeric data.
- The missing values in the "Description" column were replaced with the most occurring value in that column. (Text-generating methods were attempted but failed due to insufficient data)
- The "Keywords" column originally has 5 keywords for each website, however, I chose to split them into 5 different columns, find the correlation between each of the 5 words and the remaining features "Title", "Description", "URL" ("Number of Words" is irrelevant in this case), and assign the keyword with the strongest correlation to the "keyword_final" column. The other keyword columns are dropped.
- The cleaned data without any missing values is stored in a CSV file named "web_ML_data_cleaned" and is to be found alongside the code for the data processing in the "processing-web-scraped-data" folder.

# Tokenizing
To save a step for anyone who may potentially use this data (or maybe myself later on), I have tokenized the data. The tokenized data is to be found in the "tokenize-processed-data" folder alongside the tokenizing code.
