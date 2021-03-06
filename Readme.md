# AirXGB

## Predicting on Airbnb pricing with machine learning


## Background

### With the rise in popularity of services like airbnb, there has been a shift in who sets the pricing for short to mid-term vacation rentals. The shift is from massive hotel chains with teams of people forecasting demand based on a wealth of metrics to individuals with one or a few properties that they want to rent out as Airbnb units. The amount of domain knowledge that the average Airbnb host has is signficantly lower than people who have worked for years in the field. They can always seek the help of price tips, but due to the incentives for Airbnb to fill every unit (even at a lower price), they may sometimes find that these price tips are too low, especially if there are factors such as occaisional low ratings.

## Domain Knowledge

### I spent the majority of my life growing up in a small 30 room motel in a shore town. So my family has spent lots of time thinking about the demand and pricing for our motel rooms. The fact that we live in a shore town means theat price fluctuations happen throughout the year, and nailing it in such a way that we sell out our rooms at the highest price point can sometimes feel like more of an art than a science. Thinking about pricing when taking reservations is hard even for somebody who has been in the business of hospitality for years, so it must feel very complex to someone who has just begun renting a property on Airbnb, 

## Data

### I found the data used for this project on the webesite: insideairbnb.com. My process was that I collected the CSV's for the following cities: Austin (scraped March 2017), Boston (scraped October 2017), Wasington DC (scraped May 2017), Los Angeles (scraped May 2017), New Orleans (scraped March 2018) New York City (scraped March 2018), Portland (scraped February 2018), San Francisco (scraped March 2018), and Seattle (scraped January 2016) as they are all cities with ~4,500 rows after data cleaning. The data is available for download at: http://insideairbnb.com/get-the-data.html . These samples had a few columns which deviated for each city, but overall, each city had ~90 columns per CSV.

## Languages/Packages/Tools Used

### Numpy
### Pandas
### Sklearn
### XGBoost
### Matplotlib
### AWS EC2 (used m5.4xlarge for processing the data, temporarily storing the project, and most importantly training the models and chewing through my AWS credits)

## File Structure

### Clean.py - This was the main cleaning function, 

## Process

### After some previous EDA where I found the feature importances and predictive power of several columns to be low, the model that I am currently working with mainly revolves around the raw features of an apartment, so the number of beds, bedrooms, bathrooms, unpacked amenites column, and latitude + longitude are the things which I'm using as predictors, and the Y that I am predicting towards is the price of a room for one night + the cleaning fee. There are some othe parts of this project that I am striving towards such as trying to use more predictors and potentially implementing NLP.

### The current models I have come up with are classifiers rather than regressors. I am using random forests and XGBoost classifiers at this moment, and one of the ways in which I would like to improve my project/make it more interesting would absolutely be to evolve into a regressor to see how closely I can predict on actual prices rather than the tiers which are as follows...

#### 0-150 (budget)
#### 151-300 (mid-tier)
#### 301-400 (high tier)
#### 401-500 (Expensive)

### Note: Listings worth 0 dollars or anything over 500 have been cut off. In the case of New York, this did not cause a big loss of data. These apartments are a small subset of the larger data, and an assumption is that if an apartment is listed for 0, there is some sort of issue or typo, and if an apartment is listed over 500 per night, then I have cut it out as well for different reasons. Other places where I have made assumptions are in parts of the code related to the number of bedrooms, bathrooms, and beds. These will be mentioned at the point that they happen.

#### File Structure: At this time, there are two notebooks. 1 related strictly to plotting the data and making visuals for my presentation, and the other will be the code related to creating a model for predicting on Airbnb pricing using random forests and XGBoost, and I will include my presentation as well. The data, however, will not be included as the files are large and publically available at this time. The way that they could be used would be to get the files from InsideAirbnb, put them in a data directory at the same level as these notebooks, and then make sure to name them the same way that I had.
