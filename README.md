# Coursera Data Science Courses: Project Overview
 
* Scraped over 1,800 Coursera courses using Python and beautifulsoup
* Engineered features from the text of each course description to quantify the emphasis courses put on Python, SQL, ML, DL, R, TensorFlow, and Google Cloud.

WIP:  
* Optimized Linear, Lasso, and Random Forest regressions to reach the best model
* Built a client facing API using flask

## Resources Used

**Python Version:** 3.7  
**Packages:** pandas, numpy, json, beautifulsoup, matplotlib, seaborn, flask  
**Coursera Catalog API:** https://build.coursera.org/app-platform/catalog/

## Data collection pt.1: Catalog API

For the core data, I used customized queries to get json data from Coursera's Catalog API. The fields included in the API database are:  
* Course title
* Course type (on demand/live)
* Course description
* Course domains and subdomains
* Course id
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

## Data collection pt.2: Web scraping

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

## Data cleaning & feature engineering
* Merged instructor and partner names into the main dataset
* Parsed course domains and subdomains out of nested column
* Converted start date from unix timestamp to datetime, then transformed into courses' age in days
* Made column for number of instructors
* Made columns for two types of certificates available
* Transformed primary language into regular string
* Made columns for technical skills listed in the job description:
    * Python
    * machine learning
    * deep learning/neural networks
    * SQL
    * R studio
    * Excel
    * TensorFlow
    * Google Cloud

The output file is courses_DS_cleaned.csv.

## Exploratory Data Analysis
I examined correlations and data distributions for numerical variables, then value counts for categorical variables
WIP

## Acknowledgements
* I structured this project following Ken Jee's tutorial on his DS salary estimator project: https://github.com/PlayingNumbers/ds_salary_proj  
* The idea of scraping coursera webpages stems from this kaggle dataset: https://www.kaggle.com/datasets/siddharthm1698/coursera-course-dataset. It has less fields, but includes professional certificates and specializations aside from courses.
    * I referenced a few Kaggle notebooks affiliated with the above dataset: https://www.kaggle.com/datasets/siddharthm1698/coursera-course-dataset/code
