## SQLAlchemy Homework - Surfs Up!

I have decided to treat myself to a long holiday vacation in Honolulu, Hawaii! To help with my trip planning, I need to do some climate analysis on the area. The following outlines what I did.

![](Images/surfs-up.png)

### Step 1 - Climate Analysis and Exploration

Python and SQLAlchemy were used to do basic climate analysis and data exploration of your climatae database. ALl of the following analysis were completed using SQLAlchemy ORM queries, Panda and Matplotlib.

### Precipitation Analysis


  * Designed a query to retrieve the last 12 months of precipitation data
  
  * Selected only the date and prcp values
  
  * Loaded the query resulets into a Pandas DataFrame and set the index to the date column
  
  * Sorted the DataFrame values by date
  
  * Plotted the results using the DataFrame plot method
  
  
  ![](Images/sqlprecipitation.png) 
  
  
  ### Step 2 - Climate App
  
With the initial analysis completed, a Flask API design was developed based on queries.

#### Routes

* Home Page: A list of all available routes


* /api/v1.0/precipitation: Converted the query results to a dictionary using date as the key and prcp as the value.


* /api/v1.0/stations: Returned JSON list of stations from the dataset.


* /api/v1.0/tobs: a JSON list of temperature observations (TOBS) for the previous year.


* /api/v1.0/<start> and /api/v1.0/<start>/<end>: 
  
  * Returns a JSON list of the minimum temperature, the average temperature, and the max temperature for a given start or start-end range.
  
  * When given the start only, calculate TMIN, TAVG, and TMAX for all dates greater than and equal to the start date.

  * When given the start and the end date, calculate the TMIN, TAVG, and TMAX for dates between the start and end date inclusive.

