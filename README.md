# RNNStockPricePrediction
RNNStockPricePrediction

## Objective
The objective of this assignment is to try and predict the stock prices using historical data from four companies IBM (IBM), Google (GOOGL), Amazon (AMZN), and Microsoft (MSFT).

We use four different companies because they belong to the same sector: Technology. Using data from all four companies may improve the performance of the model. This way, we can capture the broader market sentiment.

The problem statement for this assignment can be summarised as follows:

> Given the stock prices of Amazon, Google, IBM, and Microsoft for a set number of days, predict the stock price of these companies after that window.
>
> ## Business Value

Data related to stock markets lends itself well to modeling using RNNs due to its sequential nature. We can keep track of opening prices, closing prices, highest prices, and so on for a long period of time as these values are generated every working day. The patterns observed in this data can then be used to predict the future direction in which stock prices are expected to move. Analyzing this data can be interesting in itself, but it also has a financial incentive as accurate predictions can lead to massive profits.

### **Data Description**

You have been provided with four CSV files corresponding to four stocks: AMZN, GOOGL, IBM, and MSFT. The files contain historical data that were gathered from the websites of the stock markets where these companies are listed: NYSE and NASDAQ. The columns in all four files are identical. Let's take a look at them:

- `Date`: The values in this column specify the date on which the values were recorded. In all four files, the dates range from Jaunary 1, 2006 to January 1, 2018

- `Open`: The values in this column specify the stock price on a given date when the stock market opens.

- `High`: The values in this column specify the highest stock price achieved by a stock on a given date.

- `Low`: The values in this column specify the lowest stock price achieved by a stock on a given date.

- `Close`: The values in this column specify the stock price on a given date when the stock market closes.

- `Volume`: The values in this column specify the total number of shares traded on a given date.

- `Name`: This column gives the official name of the stock as used in the stock market.

There are 3019 records in each data set. The file names are of the format `\<company_name>_stock_data.csv`.


---

## 📊 Conclusion

In this project, we developed and evaluated different recurrent neural network (RNN) architectures—specifically **Simple RNN**, **LSTM**, and **GRU**—for **time series forecasting of stock closing prices**. Our structured pipeline encompassed rigorous **data preprocessing**, **feature scaling**, **sequence generation**, **model building**, and **hyperparameter tuning** to optimize forecasting accuracy.

---

### 🔧 Data Aggregation and Preprocessing:

* Combined historical stock datasets from **four different companies**.
* Applied **feature standardization and normalization** to improve convergence in RNN training.
* Employed **sliding window techniques** to create time-series samples for supervised learning.

---

### 🧠 Model Development:

* Two primary RNN types were implemented:

  1. **Simple RNN**
  2. **Advanced RNNs** (LSTM, GRU, and Bidirectional GRU)

* Extensive **randomized hyperparameter tuning** was conducted, experimenting with:

  * Number of hidden units (32 to 128)
  * Dropout rates (0.1–0.4)
  * Activation functions (e.g., ReLU, tanh)
  * Batch sizes, learning rates, and number of epochs

---

### 📈 Performance Comparison:

Both model categories were assessed using **Mean Squared Error (MSE)**, **Mean Absolute Error (MAE)**, **Root Mean Squared Error (RMSE)**, **Mean Absolute Percentage Error (MAPE)**, and **R-squared (R²)**.

| Metric   | Simple RNN | GRU (Best) |
| -------- | ---------- | ---------- |
| MSE      | 3271.19    | **930.72** |
| RMSE     | 57.19      | **30.51**  |
| MAE      | 31.60      | **18.00**  |
| MAPE (%) | 6.05%      | **4.36%**  |
| R² Score | 0.6802     | **0.8557** |

* 🔹 **GRU-based models significantly outperformed** Simple RNNs, particularly in terms of **lower prediction errors** and **higher R²**, indicating superior generalization.
* 🔹 Use of **Bidirectional GRUs** and **LSTMs** helped capture both past and future temporal dependencies in the sequence, enhancing forecasting capability.

---

### 🔍 Key Insights and Outcomes:

* **Model Selection**: GRU and LSTM units **outperformed Simple RNNs** due to their ability to **retain long-term memory** and handle vanishing gradient issues.
* **Hyperparameter Tuning**: Performance was highly sensitive to the number of units, dropout, and activation choices. Optimal configurations typically involved **64 or 128 units**, **ReLU or tanh activations**, and **dropout rates between 0.1 and 0.4**.
* **Prediction Accuracy**: GRU/LSTM models consistently delivered **lower MSE and MAE**, reducing the risk of overfitting by using techniques like **dropout and early stopping**.
* **Error Analysis**:

  * Error distributions showed a roughly normal spread centered around zero.
  * Occasional large errors were observed during **high-volatility periods**, a common challenge in stock forecasting.
  * Residual plots showed **no major systematic bias**, indicating that errors were relatively random and not pattern-driven.
* **Business Value**: The models produced **reliable short-term predictions**, potentially useful for:

  * **Risk management**
  * **Portfolio allocation**
  * **Trading strategy refinement**
  * **Market signal generation**

---

### 🏁 Final Outcome:

* ✅ The **best overall performance** was achieved by the **tuned GRU model**, showing high accuracy and stability with minimal overfitting.
* ✅ Simple RNNs, while functional, were consistently **outperformed by more advanced architectures** in capturing complex temporal patterns.
* ✅ **Advanced RNNs** (LSTM/GRU) are recommended for real-world time series forecasting tasks, particularly in **finance**, where accurate trend prediction is crucial.


