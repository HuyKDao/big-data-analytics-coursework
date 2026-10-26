# Yelp Business & User Analytics with SQL

**Question:** How do Yelp users engage with businesses over time, which businesses and cities perform best, and what do reviewers talk about?

## Data
The [Yelp Open Dataset](https://www.kaggle.com/datasets/yelp-dataset/yelp-dataset): 174,567 businesses, 1,326,100 users, 1,098,324 tips and 3,911,218 check-in rows (about 6.5 million rows in all). A hotel reviews dataset was used for the text analysis.

## What I did
- **Cleaned the four Yelp tables in pandas:** handled nulls and types, parsed dates and reset indexes so the tables joined cleanly.
- **Wrote analytical SQL in DuckDB** to answer business questions:
  - **User engagement:** tips per user, how much influence users have through their tips, whether reviewers lean positive or negative, and which city has the most tips per user.
  - **Trends over time:** seasonal patterns in tipping, and a **rolling average of monthly reviews** using window functions.
  - **Business performance:** top restaurants by city, check-in performance, review trends over time, the tip-to-check-in ratio, and users who review low-tip businesses.
- **Analyzed text:** tokenized hotel reviews, removed stop words, ranked the most frequent words and built word clouds.

## Skills and tools
SQL (CTEs, joins, aggregations, window functions such as `ROW_NUMBER`, `LAG` and rolling `AVG ... OVER`, date functions), DuckDB, pandas, NLTK, WordCloud, Plotly, Matplotlib.
