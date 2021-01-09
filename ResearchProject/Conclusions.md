### 3. Conclusions
Discussed results, illustrated by examples(qualitative analysis), answers original research questions based on findings in study, tested outcomes for statistical significance

Some relatively simple models were tested in the making of these predictions.
Starting of with a simple [Auto Regressive(AR) model](https://github.com/georgeottens/AppliedDataScience/blob/main/Python-Graphs/AR%20model.png) with [its code](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/AR_model_klant_69_werkelijke_aantallen_2018-01_2018-03.ipynb), where data of three months was used:
`train_data = ['2019-01-01':'2019-03-25']
test_data = ['2019-03-26':'2019-04-01']`
To see how well the model was able to predict the `test_data`.

As you can see in the AR model, it did pretty well on predicting the `test_data`, because the predicting followed the real number of processed packages fairly well. But because this model was just the start of all the models, the next models were being formed.

After using the AR model, the model was expanded with the Moving Average (ARMA), Integrated Moving Average (ARIMA) and finally, the Seasonal ARIMA model (SARIMA).

With the [ARMA model](https://github.com/georgeottens/AppliedDataScience/blob/main/Python-Graphs/ARMA%20model.png), the chosen training data was `['2016-01-01':'2019-09-01']` while the test data was `['2019-09-01':'2019-10-01']`,
so the model has 3 years and 8 months of training data, with 1 month as test data.

The model has `RMSE = 271` and `R^2 = 0.73`. The smaller the RMSE and the closer R^2 gets to 1, the better the model. A perfect model would have an RMSE of 0 and an R^2 of 1.
As seen in the ARMA model it kind of follows the same sort of line as the real number of packages, but it is higher in number. This could be because of the model not having an integrated moving average.
