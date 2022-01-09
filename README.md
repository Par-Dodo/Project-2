# ETL_Project_Top_Movies

For this project, we decided use a relational database PostgresSQL to store the data for the top movies from particular years, which were extracted from CSV files and the web. 

1.	Extraction
      We used the following CSV and Website to source our data
      
	 CSV From Kaggle - https://www.kaggle.com/axeltorbenson/top-4000-movies
         Scraped IMDb Top 250 Movies - https://www.imdb.com/chart/top/
	 
      The fields of interest were:
      
          -Movie Title
          -Ranking
          -Year
          -Rating
	  
2.	Transforming
      Scrapping IMDb top 250 movies
          -Used Beautiful Soup, splinter, webdriver_manager to conduct scraping of IMDB website
          -Used comprehensive list to gather movie titles, year, and rating, ranking
          -Loaded scrapped data into pandas dataframe
	  
      Cleaning the CSV
          -Used Pandas to load CSV
          -Dropped rows with null values
          -Dropped rows with 0s
	  
      Merged dataframes
          -Merged imdb with Top_4k on “Movie Title”
3.	Loading
      Connected to PostgreSQL via sqlalchemy
      Decided to use a SQL database instead of Mongodb because all of our data was structured data
      Checked for existing database and created new if did not exist
	    Loaded our 3 tables into PostgreSQL
               Imdb
               top_4k
               merged_df
      Confirmed all data was passed as intended to PostgreSQL
