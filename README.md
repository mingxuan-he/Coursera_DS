# Coursera Data Science Courses: Project Overview
 
* Scraped over 1,800 Coursera courses using Python and beautifulsoup

WIP:
* Engineered features from the text of each course description to quantify the emphasis courses put on python, SQL, ML/DL, AWS, and spark.
* Optimized Linear, Lasso, and Random Forest regressions to reach the best model
* Built a client facing API using flask

## Code and Resources Used

**Python Version:** 3.7  
**Packages:** pandas, numpy, json, beautifulsoup, matplotlib, seaborn, flask  
**Coursera Catalog API: ** https://build.coursera.org/app-platform/catalog/

## Catalog API

For the core data, I used a customized query to get json data from Coursera's Catalog API. The fields included in the API database are:  
* Course title
* Course type (on demand/live)
* Course description
* Course domains and subdomains
* Course id
* s12n id
* Slug
* Instructor id(s)
* Partner (organization) id(s)
* Affiliated specializations
* Certificates available (verified cert, specialization)
* Primary language
* Subtitle languages
* Start date
* Instructor name (in a separate nested json dict)
* Partner (organization) name (in a separate nested json dict)

From there, I filtered courses with at lease one domain listed as "data science".

## Web scraping

I built a web scraper to scrape over 1800 DS courses on Coursera. With each course, I got the following:  
* Course star rating (0-5 stars)
* Ratings count
* Number of enrolled students
* Difficulty level (beginner/intermediate/advanced/mixed)
* Length of completion (hours)
* Instructor star rating
* Instructor ratings count
* Total number of students taught by instructor
* Total number of courses taught by instructor
* Course content rating (0-100%)
* Course content ratings count

