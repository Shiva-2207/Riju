# SussexBudgetProductions Movie Analysis

Our company, SussexBudgetProductions, faced a significant loss with our last film and is determined to make informed decisions for the next project. In this analysis, we leverage IMDB data, focusing on variables like budget, IMDB score, genre, gross, and director names. Through exploratory data analysis, hypothesis testing, and data-driven insights, we aim to guide the production of a potential blockbuster with considerations for budget constraints and profitable genres.

## Setup and Dependencies
- Ensure you have the required libraries installed: `numpy`, `matplotlib`, `scipy`, `pandas`.
- The primary dataset used for analysis is 'movie_metadata.csv'.

```python
# Standard imports
import numpy as np
from matplotlib import pyplot as plt
from scipy import stats
import pandas as pd

# File path for the movie metadata
movie_data = 'movie_metadata.csv'

# Read the movie metadata file into a Pandas dataframe
df = pd.read_csv(movie_data, index_col=None)
```

## Data Cleaning
To ensure a clear analysis, we perform data cleaning, removing duplicates and handling null values. We specifically focus on the profit column, calculated as Gross - Budget.

```python
# Adds the profit column to the dataframe after calculating it
df['profit'] = df.gross - df.budget

# Removes duplicate rows and null values
new_df = df.drop_duplicates().dropna()
```

## Exploratory Data Analysis
### Director Analysis
We analyze directors to identify those with consistent profitability within budget constraints.

```python
# Using the function datas_wth_hgh_prft() to get profitable directors
director_with_high_profit = datas_wth_hgh_prft('director_name')
```

### Genre Analysis
We explore profitable genres within budget limitations.

```python
# Using the function datas_wth_hgh_prft() to get profitable genres
genres_with_high_profit = datas_wth_hgh_prft('genres')
```

## Hypothesis Testing
We perform hypothesis testing on director George Lucas and the Horror genre to assess their impact on movie profitability.

```python
# Performing one-tailed t-test for George Lucas
p_value_george = p_value_calc('director_name', 'George Lucas')

# Performing one-tailed z-test for Horror genre
p_value_horror_genre = p_value_calc('genres', 'Horror')
```

## Summary and Recommendations
The analysis indicates that George Lucas and the Horror genre are statistically significant in ensuring profitable movies. Recommendations include choosing George Lucas as the director, producing a Horror film, or exploring Comedy|Drama|Music genre directed by George Lucas, especially for a USA release.

Feel free to use and expand upon this analysis for informed decision-making in your upcoming film projects.

**Note:** Adjustments and additions may be required based on future data updates and industry trends.
