# Weather Temperature Prediction Using SimpleRNN

## Project Overview

This project implements a Simple Recurrent Neural Network (SimpleRNN) using TensorFlow and Keras to predict daily mean temperatures from historical weather observations.

The model uses a 14-day sequence of weather data to forecast the next day's mean temperature. It also demonstrates recursive forecasting for the following seven days.

## Objectives

- Explore and preprocess historical daily weather data.
- Handle missing numerical observations.
- Normalize input features using MinMaxScaler.
- Create sequential input samples for time-series forecasting.
- Develop and train a SimpleRNN regression model.
- Evaluate model performance using RMSE, MAE, and R².
- Generate and visualize a seven-day temperature forecast.

## Dataset

The dataset contains 6,812 daily weather records and 23 original columns, including temperature, humidity, wind speed, pressure, visibility, precipitation, and cloud cover.

The model uses the following features:

- Mean Temperature (°C)
- Mean Humidity (%)
- Mean Wind Speed (km/h)

**Target variable:** Next-day Mean Temperature (°C)

**Dataset source:** Add the original Kaggle dataset URL here.

## Technologies Used

- Python
- Pandas and NumPy
- Matplotlib
- Scikit-learn
- TensorFlow and Keras
- Google Colab

## Methodology

1. Load and explore the weather dataset.
2. Convert the date column to datetime and sort observations chronologically.
3. Handle missing numerical values using time-based interpolation.
4. Normalize features using MinMaxScaler fitted on training data.
5. Create input sequences using the previous 14 days of weather observations.
6. Split the data chronologically into training (70%), validation (15%), and test (15%) sets.
7. Build a SimpleRNN model with 32 recurrent units, Dropout, and a Dense output layer.
8. Train the model using the Adam optimizer and Mean Squared Error loss.
9. Evaluate predictions using RMSE, MAE, and R².
10. Generate a recursive seven-day temperature forecast.

## Model Architecture

- SimpleRNN: 32 units, tanh activation
- Dropout: 20%
- Dense: 1 output unit for regression
- Optimizer: Adam
- Loss function: Mean Squared Error (MSE)
- Training batch size: 32
- Maximum epochs: 100, with early stopping

## Results

Test-set performance:

| Metric | Result |
|---|---:|
| RMSE | 1.834 °C |
| MAE | 1.413 °C |
| R² Score | 0.940 |

The model achieved an R² score of 0.940 on the held-out test set. Its predictions had a test MAE of approximately 1.41 °C.

## Seven-Day Forecast

The trained model generates recursive temperature predictions for the next seven days.

Since future humidity and wind speed values are unavailable, the forecasting implementation holds their most recently observed scaled values constant. This is a simplifying assumption and may limit the reliability of longer-horizon forecasts.

## Limitations

- The model uses a limited set of weather features.
- Future humidity and wind speed are assumed constant during recursive forecasting.
- Performance may vary across seasons and different weather conditions.
- The model is a learning project and is not intended to replace professional weather forecasts.

## How to Run

1. Clone or download this repository.
2. Install the required Python packages.
3. Open `weather_temperature_prediction.ipynb` in Jupyter Notebook or Google Colab.
4. Obtain the original dataset and update the dataset path in the notebook.
5. Run the notebook cells in order.

## Future Improvements

- Compare SimpleRNN with LSTM and GRU architectures.
- Include additional weather variables.
- Use actual or separately forecast future humidity and wind speed.
- Compare performance against simple baseline models.
- Tune model hyperparameters and assess performance across different seasons.

## Author

Megha Abraham

## License

Add an appropriate license if you intend to distribute this project. Check the dataset's license separately before redistributing the data.
