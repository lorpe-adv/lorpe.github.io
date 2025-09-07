## Example Code Snippets

### R: Data Cleaning and Visualization

```r
# Load necessary libraries
library(dplyr)
library(ggplot2)

# Read data
data <- read.csv("sales_data.csv")

# Data cleaning
clean_data <- data %>%
  filter(!is.na(Sales)) %>%
  mutate(Date = as.Date(Date, format = "%Y-%m-%d"))

# Visualization: Sales trend over time
ggplot(clean_data, aes(x = Date, y = Sales)) +
  geom_line(color = "steelblue") +
  labs(title = "Sales Trend Over Time", x = "Date", y = "Sales")
```

---

### Tableau: Example Workflow

1. **Connect to Data Source:**  
   Import your dataset (e.g., sales_data.csv) by clicking "Connect" in Tableau Desktop.
2. **Data Preparation:**  
   Use the "Data Interpreter" to clean your data, create calculated fields (e.g., `Profit Ratio = Profit / Sales`).
3. **Visualization:**  
   Drag "Date" to Columns, "Sales" to Rows, and choose a Line Chart to visualize sales over time.
4. **Dashboard:**  
   Combine multiple charts and add filters for interactivity.

---

### Power BI: Sample DAX Calculation

```DAX
-- Calculate Total Sales
Total Sales = SUM('Sales'[SalesAmount])

-- Create a new column for Profit Ratio
Profit Ratio = DIVIDE('Sales'[Profit], 'Sales'[SalesAmount])

-- Filter data for the last 12 months
Last12MonthsSales = 
CALCULATE(
    [Total Sales],
    DATESINPERIOD('Sales'[Date], MAX('Sales'[Date]), -12, MONTH)
)
```

---

*Feel free to adapt these snippets to your own datasets and business problems!*