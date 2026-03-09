# NHL Playoff Predictor

These notebooks document my full process of training a model to predict the playoff teams in the 2025-2026 NHL season. This analysis was performed in January 2026, and my model matched 14/16 predictions made by moneypuck.com, a hockey odds and stats website powered by a production-level model.

## Technologies
- Python
  - pandas
  - Matplotlib
  - scikit-learn
  - gradient boosted trees (XGBoost, LightGBM, CatBoost)

## My Process
I love watching hockey, but I swear I've always had a bit of a jinx. It really seemed like whenever I'd say one team would win a game, the other would always win. So, I wanted to build something that could help me make data-driven statements (!) in front of my friends to hopefully help me sound smarter!
- First, I collected season-level team data dating back to the 2008-2009 season from moneypuck.com, performed some initial data exploration, and developed a few approaches to make predictions using this dataset. In addition, playoff appearance was not in the moneypuck dataset, so I manually collected that data myself.
- For feature engineering, I tried: doing nothing (i.e. just doing the minimal amount of preprocessing for the prediction algorithms to run), manual feature engineering (by using visualizations and my (limited) domain knowledge), and feature selection using scikit-learn's RFECV.
- For the model, I tried scikit-learn's ridge regressor, random forest, K-neighbours, gradient-boosted trees, ensembles, and stacking.

The combo that gave the best results was using feature selection on a minimally preprocessed dataset (no other feture engineering) and a ridge regression model.

I also uploaded the datasets I created to Kaggle, and they got a modest amount of attention there: 
- [NHL team data by season](https://www.kaggle.com/datasets/ryanhdar/nhl-team-data-by-season-2015-christmas-2025)
- [NHL team data by season with playoff appearance column](https://www.kaggle.com/datasets/ryanhdar/nhl-team-data-and-playoff-result)

## Results and next steps
Finding a way to measure my results is not the most straightforward, as sports odds can change dramatically in just a few games. I decided a reasonable metric was to see how closely my predictions resembled moneypuck.com, a site whose predictions are relied upon by many fantasy hockey general managers and sports betters. I matched 14/16 predictions, which is not bad! The main addition I want to make to this project is to integrate a real-time data pipeline. This way, the model constantly gets fresh data from the newest NHL games, and it can update its playoff odds in real-time. 

My model's percentage odds can be viewed at the bottom of the final_model.ipynb file inside the notebooks folder. Unfortunately, but unsurprisingly and accurately, my Canucks are dead last.
