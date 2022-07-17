# ML-time-series-forecast

Proof of concept about fitting a model with the following restrictions: 

1. The dataset must be **multivariate**
2. The dependant variable should **not have stationality**, but the regressors can.
3. The prediction must be done **without providing exogenous regressors** in any point of the "future"
4. The forecast horizont must be 100


* Point 3 its essential since makes well known statisticall models such as SARIMAX and Prophet out of the game. In order to solve this problem we need to use deep learning techniques in an conveniently adapted dataset.

* The implemented model is a MLP multivariate multistep  - "one shot", wich predicts a vector of 100 observations given 300.

* The model was tested in a Walk Forward Validation with 6 steps.

# Sources 
- https://machinelearningmastery.com/multivariate-time-series-forecasting-lstms-keras/
- https://machinelearningmastery.com/how-to-develop-multilayer-perceptron-models-for-time-series-forecasting/
- https://pangkh98.medium.com/multi-step-multivariate-time-series-forecasting-using-lstm-92c6d22cd9c2
- https://www.kaggle.com/code/nicapotato/keras-timeseries-multi-step-multi-output/notebook
- https://towardsdatascience.com/lagged-mlp-for-predictive-maintenance-of-turbofan-engines-c79f02a15329
- https://www.tensorflow.org/tutorials/structured_data/time_series#baselines
