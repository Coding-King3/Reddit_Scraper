# Reddit Community post details Scraper

# What does this script do? 
The script basically scrapes data from Reddit Community pages, It extracts, Post details like Title, Author Name, Time of post published, Number of upvotes, Comments length and Post URL, The script asks for user input url as well as number of posts to be scraped. 

# Key Features 
* Uses Local Chrome profile rather than selenium profile
* Random User agents and options Arguments for not being detected by the system
* The script can also scrape the available post data if the length provided is greater than actual posts available
* Uses selenium for getting complete render page and content and then the data is scraped by sending request and BS4
* Once the data is been extracted, It's directly saved inside a excel file
* The merger of selenium + bs4 reduces memory consumption and increases scraping data speed


# Technologies Used 
* Python
* Selenium for Browser automation
* BS4 for parsing html and extracting data
* Requests for sending request to the url
* Openpyxl for Creating workbook and saving data
* Logging for saving exception logs

# Technical Challenges & Solutions
* While entering the url in the driver, the site use to show captcha validation, so for dealing with these, before loading the input url, the script first loads doamin url and then it redirects to the user input url
* Getting url as per user input length was difficult because site is dynamic and the index of the xpath / css changes when new urls are loaded, so for handling this I have implemented infinite scrolling till I get the exact count of urls as mentioned by the user. Once i get this the chrome driver stops
* As relying on selenium for scraping makes the script slow so for that I have used BS4 for parsing the page and then extracted the data
* There may be scenarios where the number of posts to scrape will be more than the posts available on the site, so for that I've added a logic in except clause which does a single scroll and retrieve the urls, so that our script doesn't stop and continues to extract data

# System Architecture 
* First the site uses automation browser to search the urls as per user entered length
* Once url are gathered it will use bs4 + request so scrape the data
* Once data is scraped it will use openpyxl to load the data in the xlsx

# Prerequisites 
* Latest version of all the libraries used in the script 
* Pycharm / Python for writing editing the code.

# Installation and Usage Guide
Github and Git 
* Download Git in your system  https://github.com/git-for-windows/git/releases/download/v2.52.0.windows.1/Git-2.52.0-64-bit.exe
* Create a new folder and press shift + right click and choose git bash, it will open a cmd type window
* Type git clone https://github.com/Coding-King3/Reddit_Scraper.git
* All files available on the github will be available in your system


Python
* Download python - https://www.python.org/ftp/python/3.14.2/python-3.14.2-amd64.exe
* Installation Python - https://www.geeksforgeeks.org/python/how-to-install-python-on-windows/
* Activating venv - https://www.w3schools.com/python/python_virtualenv.asp
* Installing libraries after activating venv - pip install selenium webdriver-manager beautifulsoup4 openpyxl requests
* If the command prompt has venv still activated you can type the script name which is Reddit_scrapper.py and hit enter, the script will run
* Once script runs you need to provide a category url from reddit.com that you want to scrape, example - https://www.reddit.com/r/github/, after entering this url you will be asked to enter the number of post you want to scrape, you can type any number


# Performance Metrics 
On an average it takes almost 8 seconds to scrape the data per url, The 8 second includes a wait time of random (3,5) seconds confirm and remaining for scraping

# Output of the data 
<img width="1832" height="266" alt="image" src="https://github.com/user-attachments/assets/29a5ef68-5d45-4fad-9188-c347a8f37282" />

# License / Disclaimer
The script is made for educational purpose only. Anyone who wants to use this script for reference / educational purpose is good to go



