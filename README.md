# AI-Powered Financial Forecasting

This project leverages machine learning to perform time-series forecasting on key financial metrics, including sales (income), expenses, cash flow, and profit. The models are designed to provide accurate, data-driven financial projections that can assist in planning, budgeting, and strategic decision-making.

## Table of Contents

- [Project Objective](#project-objective)
- [Datasets](#datasets)
- [Methodology](#methodology)
  - [Data Preprocessing](#data-preprocessing)
  - [Feature Engineering](#feature-engineering)
  - [Modeling](#modeling)
- [Technologies Used](#technologies-used)
- [Evaluation](#evaluation)
- [Results](#results)
- [How to Use](#how-to-use)

## Project Objective

The primary goal is to build an accurate, interpretable, and scalable predictive analytics solution for forecasting key financial metrics using historical daily financial data [file:11]. The solution aims to provide actionable insights to support operational and strategic planning by identifying trends and seasonal patterns in the financial data [file:11].

## Datasets

The models were developed and tested on three separate real-world financial datasets, each from a different industry, to ensure the robustness of the approach across various business behaviors and transactional volumes [file:11]. Each dataset was processed independently.

The preprocessing pipeline was designed to handle large-scale financial datasets with over 300,000 rows of transactional data [file:11].

## Methodology

The project follows a structured time-series analysis workflow, from data cleaning to model evaluation.

### Data Preprocessing

The raw financial datasets underwent a rigorous preprocessing pipeline which included [file:11]:
-   **Filtering and Validation**: Retaining only records in INR and relevant financial categories (e.g., “Income”, “Expense”) [file:11].
-   **Data Cleaning**: Removing invalid or missing financial entries and standardizing date formats [file:11].
-   **Outlier Removal**: Excluding records with values beyond three standard deviations from the mean to improve model stability [file-attachment:1].
-   **Aggregation**: Aggregating financial values to a daily frequency to create a consistent time series for analysis [file:11].

### Feature Engineering

To capture complex patterns and seasonality, a rich set of features was engineered from the time-series data [file:11]:
-   **Calendar-Based Features**: Day, month, year, quarter, and day-of-week [file:11].
-   **Event-Based Flags**: Indicators for the start/end of the month, quarter, and financial year [file:11].
-   **Cyclical Transformations**: Sine and cosine encoding of time-based fields (e.g., month, day) to capture seasonality [file:11].
-   **Lag Features**: Values from previous time steps (1, 7, 14, 30, 90, and 365 days ago) [file:11].
-   **Rolling Window Statistics**: Rolling means, standard deviations, min, and max for various windows (7, 14, 30, 90 days) [file:11].
-   **Historical Averages**: Aggregated averages by month, quarter, and year [file:11].
-   **Trend Indicator**: A feature representing the number of days since the start of the dataset [file:11].

### Modeling

Several models were evaluated, including classical statistical approaches and modern machine learning methods [file:11]:
-   **ARIMA & SARIMA**: Initially used as baseline models but struggled to capture non-linear relationships in the data [file:11].
-   **XGBoost Regressor**: This was selected as the final model. It consistently outperformed the baselines across all datasets, demonstrating superior flexibility and accuracy in handling complex, feature-rich financial data [file:11].

## Technologies Used

-   **Programming Language**: Python [file:11]
-   **Core Libraries**:
    -   `pandas` & `NumPy` for data manipulation [file:11].
    -   `XGBoost` for the core prediction model [file:11].
    -   `scikit-learn` for evaluation metrics (MAE, RMSE, MAPE) [file:11].
    -   `statsmodels` for baseline ARIMA/SARIMA models [file:11].
    -   `matplotlib` for data visualization [file:11].
-   **Development Environment**: Google Colab, Visual Studio Code [file:11]

## Evaluation

Model performance was evaluated using standard regression metrics and visual analysis [file:11]:
-   **Metrics**:
    -   Mean Absolute Error (MAE) [file:11]
    -   Root Mean Squared Error (RMSE) [file:11]
    -   Mean Absolute Percentage Error (MAPE) [file:11]
    -   **Forecast Accuracy**: Calculated as `100 - MAPE` [file:11]
-   **Visualizations**:
    -   Forecast vs. Actual graphs (daily and monthly) [file:11].
    -   Feature importance plots from XGBoost [file:11].
    -   Residual analysis plots (scatter and histograms) [file:11].

## Results

The XGBoost model's performance varied across the three datasets, highlighting the importance of data quality for predictive accuracy.

| Dataset | Income Accuracy | Expense Accuracy | Profit Accuracy | Cashflow Accuracy |
| :--- | :--- | :--- | :--- | :--- |
| **Dataset 1** | 81.51% | 74.09% | 75.46% | 77.90% |
| **Dataset 2** | 19.00% | 45.62% | 73.43% | 76.68% |
| **Dataset 3** | 83.63% | 96.18% | 89.12% | 84.49% |

**Observations** [file:11]:
-   **Dataset 3** yielded the most robust and consistent forecasts, demonstrating the impact of high-quality, well-structured data.
-   **Dataset 2** had limited data volume, resulting in poor performance for some metrics (e.g., income).
-   This comparative analysis underscores that data quality, consistency, and volume are critical for achieving reliable machine learning models in finance.

## How to Use

1.  **Clone the repository**:
    ```
    git clone <your-repository-url>
    ```
2.  **Install dependencies**:
    ```
    pip install pandas numpy xgboost scikit-learn matplotlib
    ```
3.  **Prepare your data**: Ensure your financial data is in a CSV or Excel file and matches the structure used in the preprocessing steps.
4.  **Run the Notebooks**: Open and execute the Jupyter/Colab notebooks for Income, Expense, Cashflow, or Profit. Make sure to place your data file in the correct directory.

