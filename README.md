# ML-time-series-forecast

## Summary

Proof of concept about fitting a model with the following restrictions: 

1. The dataset must be **multivariate**
2. The dependant variable should **not have stationality**, but the regressors can.
3. The prediction must be done **without providing exogenous regressors** in any point of the "future"
4. The forecast horizon must be **100**


* Point 3 its essential since makes well known statisticall models such as SARIMAX and Prophet out of the game. In order to solve this problem we need to use deep learning techniques in an conveniently adapted dataset.

* The implemented model is a MLP multivariate multistep  - "one shot", wich predicts a vector of 100 observations given 300.

* The model was tested in a Walk Forward Validation with 6 steps.

This MLP one-shot model is a good fit as a ML baseline model, the reader is encouraged to try more complex models such as based on Convolutional models or LSTMS.

## Improvements
The current notebook was developed in a short time, I would lik to appoint some improvements that can be implemented, in order : 

1. Add a baseline: Concretely I would like to test the model agains a seasonal naive forecast
2. More feature engineering: encode wind direction as numerical and encode a smoothed version of the dependant variable as regressor
3. Test more complex architectures inside the MLP scheme, I have tried some informal guesses varying the hidden neurons nº, but more research can be done (both in extension and documentation the results)
3. Give the step and try with convolution and LSTM models

## Sources 
- https://machinelearningmastery.com/multivariate-time-series-forecasting-lstms-keras/
- https://machinelearningmastery.com/how-to-develop-multilayer-perceptron-models-for-time-series-forecasting/
- https://pangkh98.medium.com/multi-step-multivariate-time-series-forecasting-using-lstm-92c6d22cd9c2
- https://www.kaggle.com/code/nicapotato/keras-timeseries-multi-step-multi-output/notebook
- https://towardsdatascience.com/lagged-mlp-for-predictive-maintenance-of-turbofan-engines-c79f02a15329
- https://www.tensorflow.org/tutorials/structured_data/time_series#baselines
