# NHL Playoff Predictor

These notebooks document my full process of training a model to predict the playoff teams in the 2025-2026 NHL season. This analysis was performed in January 2026, and based on the standings at the time, my model correctly predicted 14/16 of the playoff teams that were in a playoff spot at the time. 

## Technologies
- Python
  - pandas
  - Matplotlib
  - scikit-learn
  - gradient boosted trees (XGBoost, LightGBM, CatBoost)

## My Process
I love watching hockey, but I swear I've always had a bit of a jinx. It really seemed like whenever I'd say one team would win a game, the other would always win. So, I wanted to build something that could help me make data-driven statements (!) in front of my friends to hopefully help me sound smarter!
First, I collected season-level team data dating back to the 2008-2009 season from moneypuck.com, performed some initial data exploration, and developed a few approaches to make predictions using this dataset. Playoff appearance was not in the moneypuck dataset, so I manually collected that data myself.
- For feature engineering, I tried: doing nothing (i.e. just doing the minimal amount of preprocessing for the prediction algorithms to run), manual feature engineering (by using visualizations and my (limited) domain knowledge), and feature selection using scikit-learn's RFECV.
- For the model, I tried scikit-learn's ridge regressor, random forest, K-neighbours, gradient-boosted trees, ensembles, and stacking.

I also uploaded the datasets I created to Kaggle, and they got a modest amount of attention on there: 
- [NHL Playoff Predictor](https://github.com/ricd99/NHL_Playoff_Predictor)
- https://www.kaggle.com/datasets/ryanhdar/nhl-team-data-by-season-2015-christmas-2025
