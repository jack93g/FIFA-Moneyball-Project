Predicting football player's market value using data from the video game FIFA 21

1. Objective & Hypothesis

Objective: 

- Use a linear regression model to predict the market value of football players using statistics from FIFA 21
- Analyse the relationship between the different variables in the dataset
- Make a lineup of 11 players based on the players with the highest overall rating for their respective position and a lineup based on players with the highest potential per position

Hypothesis:

Based on my prior knowledge I assumed that the value of a player should be predictable based on the following variables from FIFA:

- age
- overall rating
- release clause
- international reputation
- total stats
- potential
- growth
- time left on contract


2. Explanation of how data was processed

- The dataset is all of the available data from the video game FIFA 2021 which was scraped from this website: https://sofifa.com
- The data includes basic info about the players from FIFA including name, age, club, nationality, overall rating as well as attacking & defending points, value, wage & release clause (amongst many others).
- After doing some basic data cleaning (dealing with NaNs, converting string columns to integers if necessary, removing unneccesary columns such as club logos etc) I did some basic analysis of the data to find out such things like the top 10 players by value, the most represented nationalities and a count of players by preferred foot.
- After this I narrowed down the data to the variables mentioned in part 1 then checked the distribution and correlation of the variables and looked for outliers. 
- I used a box cox transformation to bring the data to scale (and potentially remove some outliers), then used a function to remove the remaining outliers in order to prevent the results being skewed by a small amount of players with inflated values.
- Finally I removed what I considered to be unnecessary categorical columns (such as name, club etc which have no influence on value), then used get_dummies to encode the one remaining categorical (best position) and split the data in test/train sets and applied the linear regession model from sklearn.


3. Summary of results

- The linear regression model returned an R2 score of 0.947.
- This indicates that the variables I chose are potentially good indicators of player value.
- The model can thus be used to predict to predict future players market value.

4. Sources:

- https://www.kaggle.com/ekrembayar/fifa-21-complete-player-dataset
- https://www.kaggle.com/ketanp79/fifa-19-predicting-players-market-value#Discover-and-visualize-the-data-to-gain-insights
- https://sofifa.com


5. List of libraries used:

- pandas
- numpy
- matplotlib
- seaborn
- scipy
- sklearn
- math