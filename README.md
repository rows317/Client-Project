# Client Project    
# Using Zillow to Estimate Property Value Damage

## Problem Statement
During a disaster, it is important to model and estimate the potential or forecasted effect of the event, including damage Existing indicators of forecasted damage include disaster radius, number of structures within the affected area, population, etc. Another useful indicator is the total property value of buildings in an area. Our project seeks to provide a user with up-to-date estimate of property value in their desired area.    
For residents hoping to prepare, and local governments assessing potential relief aid requests, the ability to simply input a zipcode and receive a valuation of that area's property provides a crucial first step in preparation for a disaster.  

## Executive Summary
The goal of our project is to estimate the total residential property value of a specific zip code or neighborhood in Manhattan or Brooklyn. This information is useful when forecasting the potential damage from a natural disaster. 

In order to solve this problem, we began by collecting information from Realtor.com as well as through the Zillow API. Realtor.com provides historical and current aggregate data on every zip code in the U.S. that has a listing on their site. We were able to filter out just the Manhattan and Brooklyn zip codes which gave us a high-level look at median and average home values.

Utilizing the Zillow API, we were able to get more granular data by obtaining estimates for specific home values. We felt this gave us a more accurate view of the total property value within a zip code. In order to use the Zillow API, specific addresses are required. We collected thousands of addresses from the City of New York Open Data site.

Our function takes in an individual or list of zip codes and will return the estimated average and total property value as well as several other statistics. One limitation with the Zillow API is that it will only provide an estimate for homes that have been listed on the site. The resulting average property value is calculated from a sample set of addresses that have estimates on Zillow. We calculated the estimated total property value by multiplying the average property value by the total housing units in the zip code(s). We obtained the number of housing units through the USZipCode package in Python. 

This calculated value can be used to locate which zip code(s) or neighborhoods will have the highest estimated property value damage given a natural disaster.

We also built a visualizaton tool from Realtor.com's historical data.  Using the data we give a view of monthly or yearly trends by county, neighborhood, or zip code. The historical data was only the aggregate median and average listing price for residential properties in a given zip code, but it allows us to see general trends in the market and predict future movements.

## Limitations
- Zillow API doesn't have a comprehensive list of addresses that they have estimates for in each zip code. Therefore, it is tough to tell which addresses that we collected will have estimates unless we loop through them all.
- Finding a comprehensive list of addresses in a given area can be difficult, given privacy/spam prevention.
- Zillow API doesn't allow you to specify apartment numbers in the search. The estimate we receive is just one value from a particular building. This is particularly important in Manhattan where apartment buildings are the primary form of residence.
- Zillow API can be time intensive depending on the number of addresses inputted.
- We are only able to get estimates for homes that have been listed on Zillow. Many properties in Manhattan and Brookyln are not listed. We are estimating based off of a sample set.
- The Realtor.com historic data set is missing 16 zip codes.


## Next Steps
- Find a more comprehensive list of addresses that have property estimates.
- Create a function that uses distance as a measurement for disaster area rather than zip code.
- Find a way to value commercial real estate. Currently our model only takes into consideration residential properties.

## Conclusions & Recommendations
- Our model is a useful tool, but is not a stand alone predictor.
- Overall damage cost can be broken down into various factors: property value, value relative to building type, relative damage area  vs total property area.
- Combined with other valuation tools, what we have built offers critical information to build an overall view of damage after a disaster.




## Files and Folders
- Code Folder, 5 Files
  - [Data Cleaning 1]() - code to clean addresses and isolate zip codes
  - [Zillow Estimator]() - further data cleaning and creation of Zillow API grab function
  - [Charts]() - visualization tool using historical data
  - [Maps]() - maps for zip code/neighborhood visualization

- Data Folder
 -
 
- Visuals Folder
  - [Function Samples]() - screenshot of function outputs
  - [Folium Maps]() - maps corresponding to function outputs




- [Presentation](https://git.generalassemb.ly/Rose-TesorieroMontoya/Client-Project/blob/master/Client%20Project.pdf)

## Resources

- [NYC Neighborhood Definitions](https://www.health.ny.gov/statistics/cancer/registry/appendix/neighborhoods.htm)

- [USZIPCODE Documentation](https://uszipcode.readthedocs.io/)

- [Folium Documentation](https://python-visualization.github.io/folium/)

- [Zillow API](https://www.zillow.com/howto/api/APIOverview.htm)

- [Realtor.com Data](https://www.realtor.com/research/data/)

- [NYC Special Initiative For Resilience And Rebuilding Article](http://s-media.nyc.gov/agencies/sirr/SIRR_singles_Lo_res.pdf)


## Team Members

Andrew Bergman, Rose Tesoriero-Montoya, and Lucas Winter


