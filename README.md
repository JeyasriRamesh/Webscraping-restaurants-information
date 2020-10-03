# HEPIER--Webscraping-restaurants
Scraping location specific restaurants from google maps and its websites from google search.<br>
* Selenium * DOMS * NLP 

<b>Step 1: Automating Google Map search and extraction</b>
- Added Selenium and WebDriver libraries to start with.
- Got runtime inputs on Location and no. of restaurant details to be scraped.
- Calculated the number of pages to be scraped (Google map displayes 20 results per page)
- Initialized webdriver
- Accessed Google map search bar using Xpath and Enter key instead of search button
- Performed search with keywords -> Location + 'restaurants'
- Analysed the structure of data displayed using Inspect element (Chrome)
- Identified the XPath of Restaurant names
- Iterated through the XPath
- Added sleep time for pages to load before and after clicks.
- Extracted Restaurant names and performed a automated click on each restaurants.
- Handled exceptions
- Indentified XPath of the address content and extracted them
- Navigated back to the search results of page 1
- Repeated the same for all results in page 1
- Navigated to consecutive pages if required
- Stored the restaurant names and the addresses in an array


<b>Step 2: Restaurant URL extraction</b>
I faced an issue with extractign the website URL directly from the google map results. 
So I did a work around by extracting them by automating a google search.
- Performed an automted search with the Restaurant name + city as keyword
- Iterated through the XPath
- Added sleep time for pages to load before and after clicks.
- Retrieved the title and Xpath of the first 10 results
- Handled exceptions
- Used FuzzyWuzzy library to calculate the token set ratio for the restautant name and the titles of the retrieved search results
- Stored the Xpath id and the search result's scores in a list of dictionaries
- Retrieved the search result that has high score (levenshtein distance)
- Identified the URL of that particular search result and retrieved it


<b>Step 3: Storing data</b>
- Initialized a dataframe 
- Dumped array data to the dataframe 


<b>Room for Improvement:</b>
- URL extraction from the home site and ignoring aggregator websites
- URL extraction from google map results
- Experimenting the same with Google Maps API
- Code optimization
