# DSA-210-Project


DSA 210 Project Proposal
Do EA Sports FC 25 Player Ratings Reflect Real Market Value?

# 1. Motivation:
Football game simulations like EA Sports FC 25 assign player ratings meant to represent their real performance. This project asks whether these ratings are parallel to actual market values of footballers during the 2024 season. Understanding this link combines sports economics with data science and this combination is one of the areas containing the most statistical data. The research question is “How strongly do EA FC 25 ratings correlate with real player market values?”.

# 2. Data Source
Two publicly available and free Kaggle datasets will be used:
 ## 1.	EA Sports FC 25 Dataset
      https://www.kaggle.com/datasets/nyagami/ea-sports-fc-25-database-ratings-and-stats/data
      For players’ overall ratings and attributes.
 ## 2.	Transfermarkt Dataset
      https://www.kaggle.com/datasets/davidcariboo/player-scores/data?select=player_valuations.csv
      For players’ real market values.

# 3. Data Analysis Plan
  ## 1.	Data Preparation:
        Merge the two datasets by player name, nationality, and club.
    	Filter the market value data to the 2024 season.
    	Clean inactive players.
    	Convert all market values to a common currency (EUR).
    	Categorize by position.
  ## 3.	Exploratory Data Analysis (EDA):
      Visualize the distributions of ratings and market values.
      Calculate correlation coefficients between overall rating, and market value.
      Generate scatter plots and heatmaps to show patterns by position and age.
      Conduct simple hypothesis testing.
  ## 4.	Visualization:
      Correlation heatmaps, scatterplots, and ranking of “most undervalued” players.

# 4. Expected Findings
Is there a strong positive relationship between EA ratings and market values?
Which player features explain deviations?
Are there biases or outliers?

# 5. Limitations
EA ratings are and may lag behind real life performance updates.
Market values are estimated, not actual transaction amounts.
Some player name duplicates may cause matching errors.

