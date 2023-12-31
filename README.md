
# Final-Project-Statistical-Modelling-with-Python

## Project/Goals
The goal of this project is to study the bikeshare business in a city of choice and find out the relationship between the usage of bikes and attributes of the points of interests around the bike stations in the city. 

For the purpose of this project, multiple data sources have been used which are as listed below:
    

 1. [Citybikes API](https://citybik.es/)   
 2. [Foursquare Places API](https://developer.foursquare.com/places)   
 3. [Yelp API](https://www.yelp.com/developers/documentation/v3/get_started)

## Process
The following process was followed to perform the data analysis:

### Step 1: Data extraction
    
 1. Explore Citybikes API and pick a city of choice to pull data from. The data pulled from the API was stored locally in a CSV file. 
 2. Exploration and testing of Foursquare and Yelp APIs to decide the course of action to parse the output after invoking the API.       
 3. By making use of the bike station information extracted from the Citybikes data, the Foursquare and Yelp APIs were invoked to pull data corresponding to each station. The incoming JSON was parsed to extract relevant data.        
 4. Date extracted from Foursquare and Yelp APIs were stored into local files in preparation for the next step.       
 5. Retrieved the list of top 10 rated restaurants in the city.

    
### Step 2: Joining data and perform EDA

 1. In this step of the project, data from Foursquare and Yelp APIs were merged into a single dataset.
 2. Next, a series of data quality checks were performed such as percentage of fullness of data(null value check), duplicate check, visualizing data points to understand the distribution of data. 
 3. Thereafter, the cleaned data was loaded into a newly created SQLite database.

    
### Step 3: Model building and regression analysis
    

 1. In this step a series of data analysis steps were performed.    
 2. As a first step, the data from the previous step was utilized to form the datasource for analysis. 
 3. Using **matplotlib** library, a line plot was implemented to study relationship between free bikes in a station and its relationship with the rating of POIs around the bike stations. Another line plot was implemented to study the relationship between free bikes in a station and distance of POIs from the bike station.    
 4. Next **statsmodel** package was utilized to perform linear and multilinear regression analysis on dependent variable "No of free bikes" by using independent variables such as POI rating, POI distance, location etc.
 5. As a stretch activity, a classification model was implemented to understand the correlation between bike availability and POI attributes.
    

## Results
A dataset of 25K records was retrieved initially from the APIs. However, data cleanup process resulted in the dataset size to reduce by about 7K and therefore there were 18K+ records to deduct analysis from.

The study of relationship between free bikes in a station and rating of POI indicates that the rating of POI has impact on the number of free bikes in a bike station. The number of free bikes in a station are lower for stations that have high rating for the points of interest in the bike station's vicinity.

With a lower regression coefficient, the study of relationship between free bikes in a station and distance from POI indicates that its a weak relationship. However, the study indicates that there are lesser free bikes where POI is closer to the bike station, i.e, bike-share consumption is high when the POIs are closer.

## Challenges 
The following were the main challenges encountered as part of this data analysis:
    

 1. The intepretation of results from the APIs were challenging. The documentation that was available for Citybikes API was very limited.    
 2. The next challenge was in parsing the results from the Foursquare and Yelp APIs. The normalize function in Pandas library turned out to be a very handy tool to tackle this challenge.    
 3. The Foursquare API did not provide ratings for the POI. This impacted the dataset negatively in the cleanup process.    
 4. The next challenge was in dissecting the data to decide on the variables to use for data analysis.    
 5. Making meaningful and reliable inferences from the linear and logical regression analysis was another challenging step in the process.

## Future Goals
If I had more time, I would like to take the data analysis to the next level by considering the impact of POI categories and its impact on the bike usage rate. 

I would also like to study the results deeper to make meaningful inferences from the results of the regression models.
