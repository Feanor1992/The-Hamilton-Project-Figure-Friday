# The-Hamilton-Project-Figure-Friday

## Project Overview ##

This project is designed to provide an interactive and comprehensive analysis of the US federal expenditures dataset. The dashboard offers multiple visualizations that help users explore trends in federal outlays over time, identify top spending categories, and observe dynamic changes in spending patterns. By integrating advanced data processing techniques with interactive visualizations, the project offers valuable insights into federal spending behavior.

## Key Components and Features ##

1. **Data Processing and Cleaning**
    - ***Data Ingestion:*** The project reads data from a CSV file containing federal outlays.
    - ***Cleaning:*** Rows with missing critical values (such as `Date`, `Daily`, or `transaction_catg_renamed`) are dropped to ensure data integrity.
    - ***Type Conversion:*** The `Date` column is converted to a datetime format, and the `Daily` column is converted to a numeric type, with non-numeric values replaced by 0.
    - ***Sorting:*** Data is sorted chronologically to facilitate time series analysis.
2. **Feature Engineering and Additional Analytics**
    - ***New Temporal Features:***
        - *Month:* Extracted from the `Date` column (converted to a timestamp for the start of each month).
        - *Year:* Extracted from the `Date` column.
    - ***Category Simplification:*** A shortened version of the spending category name is created to enhance readability in visualizations.
    - ***Aggregations:***
        - *Daily Total Spending:* Grouping data by date to compute overall daily expenditures.
        - *7-Day Moving Average:* Calculation of a rolling average to smooth short-term fluctuations.
        - *Monthly Aggregation:* Total spending per month is computed, along with the percentage change from month to month.
        - *Cumulative Spending:* The cumulative sum of daily spending is calculated to show how spending accumulates over time.
    - ***Category-Level Analysis:*** For the latest month, spending is aggregated by category. The project highlights the top 10 spending categories, with any additional categories grouped under an "Others" label.
3. **Visualizations**
The dashboard includes several interactive charts, each serving a specific analytical purpose:
    - ***Line Chart – Total Monthly Outlays:***
        - Displays the total federal outlays per month with a built-in range slider for detailed time exploration.
    - ***Bar Chart – Top 10 Spending Categories:***
        - Shows the leading spending categories for the most recent month.
    - ***Pie Chart – Spending Distribution:***
        - Visualizes the proportion of spending per category, including a segment for "Others" if applicable.
    - ***Heatmap – Monthly Spending by Top N Categories:***
        - To improve readability, the heatmap is limited to the top 20 categories based on overall spending. The chart includes rotated x-axis labels and an increased figure size for clarity.
    - ***Daily Spending with 7-Day Moving Average:***
        - Compares daily spending figures with their 7-day rolling average, highlighting short-term trends.
    - ***Monthly Percentage Change:***
        - Displays month-over-month changes in total spending as a bar chart, which helps identify periods of rapid increase or decrease.
    - ***Cumulative Spending:***
        - Illustrates the cumulative federal outlays over time to provide a long-term perspective on spending accumulation.
4. **Dashboard Interface and User Experience**
    - ***Interactive Dropdown Menu:***
        - Users can switch between different visualizations using a dropdown menu. Special styling ensures that the dropdown text is clearly visible (black text on a white background), even when integrated with a dark-themed dashboard.
    - ***Dark Theme Integration:***
        - The dashboard uses the CYBORG Bootstrap theme for a modern dark appearance, which is applied consistently across all visualizations.
    - ***Responsive Layout:***
        - The dashboard layout is built with Dash Bootstrap Components (DBC) to ensure responsiveness and ease of navigation.
5. **Technologies and Libraries**
    - ***Python & Pandas:*** For data processing, cleaning, and feature engineering.
    - ***Plotly Express and Plotly Graph Objects:*** For creating a variety of interactive charts and visualizations.
    - ***Dash and Dash Bootstrap Components:*** For building the web-based dashboard and handling interactive user inputs.
    - ***Custom Styling:*** Inline styling and configuration options are used to ensure the interface is both visually appealing and functional.
