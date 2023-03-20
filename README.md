# Mission-to-Mars
This mission to Mars analysis will use full webscraping on the [Mars NASA news site](https://redplanetscience.com/) to identify HTML elements on a page, identify the `id` and `class` attributes, and extract information *(including HTML tables and recurring elements like multiple news articles)* via both automated browsing with Splinter and HTML parsing with Beautiful Soup.

## Overiew of Analysis
From the [Mars NASA news site](https://redplanetscience.com/), this data analysis project will scrape titles & preview text from Mars news articles as well as scrape & visually analyze Mars weather data *(which exists in a table)*. 

### **Scrape Titles and Preview Text from Mars News**
Using Splinter and HTML parsing with Beautiful Soup in [part_1_mars_news.ipynb jupyter file](https://github.com/vzhang90/Mission-to-Mars/blob/main/part_1_mars_news.ipynb), the Titles and Preview Text from [Mars News](https://redplanetscience.com/) were scraped following:
1. automated browsing to visit the [Mars NASA news site](https://redplanetscience.com/)
    - inspect the page to identify which elements to scrape
2. created a Beautiful Soup object in order to extract text elements from the website
3. extracted the titles and preview text of the news articles scraped
    - storing the scraping results in Python data structures as follows:
        - Store each title-and-preview pair in a Python dictionary. And, give each dictionary two keys: title and preview
        - Store all the dictionaries in a Python list
        - Print the list in your notebook
4. the final data was exported to a JSON file [mars_news.json](https://github.com/vzhang90/Mission-to-Mars/blob/main/mars_news.json)

### **Scrape and Analyze Mars Weather Data**
The code in the jupyter file [par_2_mars_weather.ipynb](https://github.com/vzhang90/Mission-to-Mars/blob/main/part_2_mars_weather.ipynb) scrapes and analyzes Mars weather data following these steps:
1. automated browsing to visit the [Mars Temperature Data Site](https://data-class-mars-challenge.s3.amazonaws.com/Mars/index.html)
    - inspect the page to identify which elements to scrape
2. created a Beautiful Soup object and used it to scrape the data in the HTML table
    - can also be achieved by using the Pandas `read_html` function
3. assembled the scraped data into a Pandas DataFrame. The columns should have the same headings as the table on the website accordingly:
    - `id`: the identification number of a single transmission from the Curiosity rover
    - `terrestrial_date`: the date on Earth
    - `sol`: the number of elapsed sols (Martian days) since Curiosity landed on Mars
    - `ls`: the solar longitude
    - `month`: the Martian month
    - `min_temp`: the minimum temperature, in Celsius, of a single Martian day (sol)
    - `pressure`: The atmospheric pressure at Curiosity's location
4. examined the data types that were currently associated with each column
    - if necessary, cast (or convert) the data to the appropriate `datetime`, `int`, or `float` data types
5. analyzed dataset by using Pandas functions to answer the following questions:
    - How many months exist on Mars?
    - How many Martian (and not Earth) days worth of data exist in the scraped dataset?
    - What are the coldest and the warmest months on Mars (at the location of Curiosity)? To answer this question:
        - Find the average the minimum daily temperature for all of the months
        - Plot the results as a bar chart
    - Which months have the lowest and the highest atmospheric pressure on Mars? To answer this question:
        - Find the average the daily atmospheric pressure of all the months
        - Plot the results as a bar chart
    - About how many terrestrial (Earth) days exist in a Martian year? To answer this question:
        - Consider how many days elapse on Earth in the time that Mars circles the Sun once
        - Visually estimate the result by plotting the daily minimum temperature
6. export the DataFrame to a CSV file
