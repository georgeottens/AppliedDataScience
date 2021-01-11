## 3. Conclusions
Discussed results, illustrated by examples(qualitative analysis), answers original research questions based on findings in study, tested outcomes for statistical significance

## AR
Some relatively simple models were tested in the making of these predictions.
Starting of with a simple [Auto Regressive(AR) model](https://github.com/georgeottens/AppliedDataScience/blob/main/Python-Graphs/AR%20model.png)/[Code](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/AR_model_klant_69_werkelijke_aantallen_2018-01_2018-03.ipynb), where data of three months was used:
`train_data = ['2019-01-01':'2019-03-25']
test_data = ['2019-03-26':'2019-04-01']`
To see how well the model was able to predict the `test_data`.

As you can see in the AR model, it did pretty well on predicting the `test_data`, because the predicting followed the real number of processed packages almost directly.
But because this model was just the first one of all the selected models, the next models were being formed to see if they would perform any better.

After using the AR model, the model was expanded with the Moving Average (ARMA), Integrated Moving Average (ARIMA) and finally, the Seasonal ARIMA model (SARIMA).

## ARMA
With the [ARMA model](https://github.com/georgeottens/AppliedDataScience/blob/main/Python-Graphs/ARMA%20model.png)/[Code](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/ARMA_model_klant_69.ipynb), the chosen training data was `['2016-01-01':'2019-09-01']` while the test data was `['2019-09-01':'2019-10-01']`,
so the model has 3 years and 8 months of training data, with 1 month as test data.

The model has `RMSE = 271` and `R^2 = 0.73`. The smaller the RMSE and the closer R^2 gets to 1, the better the model.
A perfect model would have an RMSE of 0 and an R^2 of 1.
As seen in the ARMA model it kind of follows the same sort of line as the real number of packages, but it is higher in number.
This could be because of the model not having an integrated moving average.

## ARIMA
The ARIMA model was tested with [stationary data](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/ARIMA_model_klant_69_YEET.ipynb) and [real values](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/ARIMA_model_klant_69_YEET_werkelijk.ipynb).

### Stationary:

Stationary data was formed by taking the difference in number of packages related to yesterday.
The specifications were `train_data = ['2018-01-01':'2020-01-01]` with `test_data = ['2019-12-01':'2020-01-01']`.
This means the model has already seen the real values during the time of the predicted values.
This is not a good way to show results because the model has been effected by the real values.
At the time making a prediction without any "seen" data was not within reach.

### Real values:

As can be seen in the code, the real values did not quit work for this model.
The model predicted a straight line which was the mean of the total number of packages during the whole dataset.
Trying to make a model that functioned properly did not work at that time.

A conclusion was drawn that this model did not function well enough, because of the missing seasonal elements, that can be specified with the SARIMA model, so this model was being formed.

## SARIMA
The SARIMA model was, as to be expected, the best model to be used for our dataset.
While not performing any extras relating splitting the dataset, applying cross-validation, or any other kind of conformation, the model was also being formed with `train_data = ['2018-01-01':'2020-01-01']` and `test_data = ['2019-12-01':'2020-01-01']`.
This meant that this model was also contaminated.

After having a meeting about splitting the dataset in [train/validation/test](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/SARIMA_model_klant_69_train_val_test_optimaliseren.ipynb) sets with stationary data, the model was trained with the training set only, while predicting the values of the validation set.
This was the right way to apply a model.
The model has an `RMSE = 151` and `R^2 = 0.34`.
When looking into the ARMA model, this model has a lower RMSE which is good, but a lower R^2 aswell, which means that the model has more diviation then the ARMA model.
As can be seen the model predicted the beginning of the validation set fairly well, but oscillated a little towards the 0 point of the graph.
The end of the validation set was not predicted even close to the real values.

To make up for this error, cross validation came in play.
Everytime the model predicted a value, the real value was put into the training set and the model predicted the next day and so on.
This is also called; Rolling Window.
This kind of cross validation was done with real values and stationary data.

### Rolling Window
#### Real values:
The Model with real values and rolling window came out like [this](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/SARIMA_model_klant_69_rolling_window_werkelijk.ipynb).
It has no specified RSME and R^2, because this was a different method of forming the model, and at the time performing RMSE and R^2 on this model was unfamiliar to the group.
An evaluation on looking at the model, this was the best model so far.
The model with the [natural log](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/SARIMA_model_klant_69_rolling_window_werkelijk_log.ipynb) did not result in a better prediction then the previously mentioned model.
In fact the model was unclear to others because of the log that was applied to the dataset, so the real numbers of packages and predicted was unknown.
The model with an attempt of [filtering peaks](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/SARIMA_model_klant_69_rolling_window_werkelijk_pieken_filteren.ipynb) was not formed.
This is because it was to difficult to filter peaks relating to real values at the time.

For Rolling Window Real Values, the Regual Rolling Window came out as best.

#### Stationary data:
The techniques that were applied on the stationary rolling window were the same as for the real values.
- [Regular Rolling Window](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/SARIMA_model_klant_69_rolling_window_verschil.ipynb)
- [Natural log](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/SARIMA_model_klant_69_rolling_window_verschil_log.ipynb)
- [Filtering peaks](https://github.com/georgeottens/AppliedDataScience/blob/main/Python_Notebooks/SARIMA_model_klant_69_rolling_window_verschil_pieken_filteren.ipynb)

Because of the stationary data, the RMSE could be formed again.
- Regular Rolling Window `RMSE = 184`
- Natural log `RMSE = 233`
- Filtering peaks `RMSE = 155`

When looking into the data, the model that looks the most promising is the regular rolling window.
It misses some peaks, but still performs better then the natural log and filtering peaks.
The natural log almost completely misses every peak, which is the most crucial prediction.
Filtering peaks did not result in a better prediction for the rest of the data.

For Rolling Window Stationary Data, the Regular Rolling Window came out as best.

Concluding SARIMA, the best model is the Regular Rolling Window using Real Values.
This is because the graph is easy to interpret, and the biggest miss in peak, is no problem according to PostNL.

## Final Conclusion:
From all the models formed in this project, the SARIMA model using real values and a rolling window came out as the best model.
Although the RMSE and R^2 could not be formed, PostNL has concluded that this is the best model to be used for their purposes.
