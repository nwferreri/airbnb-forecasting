# Airbnb Forecasting Product

## Goal
Create an ensemble forecasting product to predict Airbnb demand in New York state for the next month.

## Data
Daily data spanning ~2200 days. Features include:
* `Demand`
* `Easter`, `Thanksgiving`, `Christmas` - holiday indicators
* `Temperature`
* `Marketing`

## Analysis
Exploratory data analysis was performed to gain some initial insights into the data.

Summary statistics showed that there is enough variability in the data to imply some kind of seasonality.

Quarterly seasonality is represented in **Figure 1** below:<br>
![image](https://github.com/nwferreri/airbnb-forecasting/assets/112211174/39933e97-18e4-489a-8ba5-d966e31c0d29)<br>
**Figure 1**: Black lines show yearly trends for each quarter. Red lines show average seasonality for the quarters across all years.

The relationship between Temperature and Demand was also explored in **Figure 2** below:<br>
![image](https://github.com/nwferreri/airbnb-forecasting/assets/112211174/de97cdfb-e5b2-4259-9651-e4031accb40c)<br>
**Figrue 2**: There is a clear negative correlation between temperature and demand. Vertical dotted blue lines indicate Easter (left) and Christmas (right).

Finally, an auto-correlation plot was generated, seen in **Figure 3** below:<br>
![image](https://github.com/nwferreri/airbnb-forecasting/assets/112211174/c4b323de-00f4-40e7-8116-7af9f026cbc4)<br>
**Figure 3**: Periodic peaks in multiples of 7 indicate that there is information in the past for this data.

## Modeling and Parameter Tuning
Four models were used for this project: Prophet, SARIMAX, Silverkite, and LSTM.

Initial models were generated and then parameter tuning with cross-validation was performed. Best parameters for each model were selected based on root mean squared error and were exported.

Forecasting models were created using the best parameters for each model and their predictions were exported.

## Ensemble Model
The predictions from all four models were combined into an ensemble model. The errors were extracted and used to weight the predictions of each model. The results are visualized in **Figure 4** below:<br>
![image](https://github.com/nwferreri/airbnb-forecasting/assets/112211174/8cc9987f-ed0a-4cb9-88ec-912fde8c4fa0)<br>
**Figure 4**: Results from all 4 models and the ensemble combination of them.
