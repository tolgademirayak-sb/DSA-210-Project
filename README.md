# DSA-210-Project


DSA 210 Project Proposal
Do EA Sports FC 25 Player Ratings Reflect Real Market Value?

# 1. Motivation:
Football game simulations like EA Sports FC 25 assign player ratings meant to represent their real performance. This project asks whether these ratings are parallel to actual market values of footballers during the 2024 season. Understanding this link combines sports economics with data science and this combination is one of the areas containing the most statistical data. The research question is “How strongly do EA FC 25 ratings correlate with real player market values?”.

# 2. Data Source
Two publicly available and free Kaggle datasets used:
 ## 1.	EA Sports FC 25 Dataset
      https://www.kaggle.com/datasets/nyagami/ea-sports-fc-25-database-ratings-and-stats/data
      For players’ overall ratings and attributes.
 ## 2.	Transfermarkt Dataset
      https://www.kaggle.com/datasets/davidcariboo/player-scores/data?select=player_valuations.csv
      For players’ real market values.

# 3. Data Analysis
  ## 1.	Data Preparation:
     Merged the two datasets by player name, nationality, and club.
    	Filter the market value data to the 2024 season.
    	Clean inactive players.
    	Convert all market values to a common currency (EUR).
    	Categorize by position.
  ## 2.	Exploratory Data Analysis (EDA):
     Histograms of "OVR" and "log market value".
     Correlation between **OVR** and `log_value_2024`.
     Heatmaps:
       Position × Market value bins
       Age × Market value bins
     Hypothesis tests:
        Correlation test: is the OVR–value correlation statistically significant?
        t-test: high-rated players (OVR ≥ 85) vs low-rated players (OVR < 80).
        ANOVA across positions and age groups.
  ## 3.	Supervised Learning (Regression):
     Modeled `log_value_2024`as Y 
     For X: used EA attributes, age, positions and leagues
     Splited the data into train and test sets , fit a "Linear Regression" model, and evaluate it with RMSE, MAE and R² on the test set.  
     Refitted the model on the full dataset, computed predicted values and "value_gap_eur = market_value_2024_eur − pred_value_eur" 
     Used this to identify the 10 most undervalued players.
  ## 4.Unsupervised Learning:
     I applied "k-means clustering (k = 4)"
     Features: `OVR`, `PAC`, `SHO`, `PAS`, `DRI`, `DEF`, `PHY`, `age_2024`
     For each cluster, I computed "Number of players", "Average ratings", "average age", "average market_value_2024_eur"
     This gives us player types which are "High OVR, prime age attacking players with the highest average market value", "Young, lower OVR but relatively pacey players with modest all-round stats and low average market value", "Prime age defensive players (high DEF and PHY) with mid    range market values", "Average OVR, defensively oriented players with very low attacking stats and relatively low market values".
     
# 4. Main Insights
EA OVR has a strong, statistically significant positive correlation with log market value.
High-rated players (OVR ≥ 85) are significantly more valuable than low-rated players.
Attacking, prime age players tend to have the highest average market values.
Supervised models using EA stats, age, position and league achieve high R², showing that EA ratings contain real information about market values.
Unsupervised clustering reveals distinct player profiles, with clear differences in average market value across clusters.

# 5. Limitations
EA ratings are and may lag behind real life performance updates.
Market values are estimated, not actual transaction amounts.
Some player name duplicates may cause matching errors.
