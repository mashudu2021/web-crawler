# web-crawler
Overview
The project is designed to crawl the web, gather information about web pages and their links, store this information in a database, and then visualize the results using a graph. It consists of several scripts that work together to accomplish this.

Components
Web Crawling (spider.py)

Purpose: This script crawls web pages starting from a specified URL and stores information about each page and its links in a database.

How It Works:

Connects to a SQLite database (spider.sqlite).
Creates tables to store page details and links between pages.
Starts crawling from a given URL or resumes from where it left off.
For each page, it retrieves the HTML content, extracts links, and updates the database with this information.
Ranking Pages (sprank.py)

Purpose: This script computes the importance or "rank" of each web page using algorithms like PageRank.

How It Works:

Reads the page and link data from the database.
Applies a ranking algorithm to determine the importance of each page.
Updates the database with the new ranks for each page.
Generating JSON for Visualization (spjson.py)

Purpose: This script prepares data in JSON format for visualizing the web pages and their connections.

How It Works:

Extracts page data and ranks from the database.
Normalizes the ranks and formats the data as JSON.
Writes this JSON data to a file (spider.js) which will be used for creating the visual graph.
Exporting Data for Visualization (sprest.py)

Purpose: This script may handle exporting or interacting with web services for visualization, though its specific details are not provided.

How It Might Work:

Could be used to handle RESTful API interactions, but specifics depend on the implementation details not included here.
Data Flow
Crawling the Web:

Start with a base URL and use spider.py to visit pages, collect their HTML, and discover links to other pages.
Store all this information in the spider.sqlite database.
Computing Page Ranks:

Use sprank.py to analyze the links and compute a ranking for each page based on its importance.
Preparing Visualization Data:

Use spjson.py to convert the database information into a JSON format suitable for visualizing the web structure in a graph.
Viewing the Results:

Open force.html in a web browser, which uses the JSON file (spider.js) to display a visual representation of the pages and their links.
![pagerank](https://github.com/user-attachments/assets/1d8d2d65-47cb-4d3f-aa0f-b48c3f23f1c3)


Summary
Crawl: Collect data about web pages and links.
Rank: Calculate the importance of each page.
Visualize: Convert the data to a format for graphical representation and view it in a web browser.
This project helps you understand the structure of a website by showing how pages are connected through links and how important each page is based on the connections.



