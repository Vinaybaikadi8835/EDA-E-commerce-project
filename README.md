# 📊 EDA E-commerce Project

## 📌 Project Overview

This project performs **Exploratory Data Analysis (EDA)** on an e-commerce sales dataset using Python.

The objective is to understand sales patterns, customer purchasing behavior, order trends, and country-wise spending through **data cleaning, transformation, aggregation, and visualization**.

The original dataset contains **541,909 records and 8 columns**.

---

## 🗂️ Dataset

The dataset contains the following columns:

| Column        | Description                             |
| ------------- | --------------------------------------- |
| `InvoiceNo`   | Invoice number associated with an order |
| `StockCode`   | Product/stock code                      |
| `Description` | Product description                     |
| `Quantity`    | Quantity purchased                      |
| `InvoiceDate` | Date and time of the transaction        |
| `UnitPrice`   | Price per unit                          |
| `CustomerID`  | Customer identifier                     |
| `Country`     | Customer's country                      |

The columns were renamed into a more Python-friendly format such as `invoice_num`, `stock_code`, `quantity`, `invoice_date`, `unit_price`, `cust_id`, and `country`.

---

## 🛠️ Technologies Used

* **Python**
* **Pandas**
* **NumPy**
* **Matplotlib**
* **Jupyter Notebook**

---

## 🔍 Data Analysis Process

### 1. Importing Libraries

The project begins by importing the required Python libraries:

* Pandas
* NumPy
* Matplotlib

### 2. Loading the Dataset

The dataset is loaded using Pandas:

```python
df = pd.read_csv("data.csv", encoding="ISO-8859-1")
```

### 3. Understanding the Dataset

Initial exploration includes:

* Dataset shape
* First and last five rows
* Column names
* Data types
* DataFrame information
* Missing-value inspection

## The dataset contains missing values particularly in `description` and `cust_id`. The notebook identifies the missing customer IDs as an important data-quality issue requiring further investigation.

## 🧹 Data Cleaning & Transformation

The project performs several preprocessing operations.

### Column Renaming

The original column names are converted to lowercase, descriptive names:

```text
InvoiceNo      → invoice_num
StockCode      → stock_code
Description    → description
Quantity       → quantity
InvoiceDate    → invoice_date
UnitPrice      → unit_price
CustomerID     → cust_id
Country        → country
```

### Date Transformation

`invoice_date` is converted into a datetime format and additional time-based features are created:

* `year_month`
* `month`
* `day`
* `hour`

The transformed dataset therefore allows the analysis to be performed across different time periods.

### Amount Spent

A new `amount_spent` variable is created to analyze the monetary value of transactions.

This enables customer-wise and country-wise spending analysis.

---

## 📈 Exploratory Data Analysis

The project explores several important business questions.

### 📅 Orders by Day

The number of orders is analyzed for different days of the week.

The analysis shows the highest number of orders on the **4th day represented in the dataset**, with 4,033 orders, while the 7th day has the lowest count at 2,169.

### 📆 Monthly Analysis

Order frequency is analyzed across the available months from **December 2010 to December 2011**.

### 👤 Customer-wise Orders

Customer purchasing activity is analyzed by grouping transactions by `cust_id` and country.

The resulting customer-level dataset contains **4,347 customer-country combinations** in the analysis.

### 💰 Customer-wise Spending

The project calculates the total amount spent by individual customers:

```python
df_new.groupby(by=['cust_id','country'])['amount_spent'].sum()
```

This allows customers with higher purchasing value to be identified.

### 🌍 Country-wise Orders

The number of orders is analyzed for different countries using:

```python
df_new.groupby('country')['invoice_num'].count()
```

The project also visualizes country-wise order counts using horizontal bar charts.

### 🌎 Country-wise Spending

Total spending is calculated for each country.

The analysis shows that the **United Kingdom** has by far the highest total spending in the dataset, followed by countries such as the Netherlands, EIRE, Germany, and France.

---

## 📊 Visualizations

The project contains visualizations for:

* 📅 Orders by day
* 📆 Order frequency by month
* 👤 Number of orders by customer
* 💰 Money spent by customer
* 🌍 Number of orders by country
* 💵 Money spent by country

These visualizations help identify patterns and differences in customer and sales behavior.

---

## 💡 Key Analysis Areas

The project focuses on answering questions such as:

1. How many orders are placed on different days?
2. How does order frequency change across months?
3. Which customers place the most orders?
4. Which customers spend the most money?
5. Which countries generate the most orders?
6. Which countries contribute the most revenue?
7. How does customer purchasing behavior vary across countries?

---

## 📁 Project Structure

```text
EDA-E-commerce-project/
│
├── EDA PART-1.ipynb       # Jupyter Notebook containing the analysis
├── EDA PART-1.html        # HTML version of the notebook
├── data.csv               # E-commerce dataset
├── README.md              # Project documentation
└── .gitignore             # Git ignore configuration
```

---

## 🚀 How to Run the Project

### 1. Clone the repository

```bash
git clone https://github.com/Vinaybaikadi8835/EDA-E-commerce-project.git
```

### 2. Navigate to the project directory

```bash
cd EDA-E-commerce-project
```

### 3. Install the required libraries

```bash
pip install pandas numpy matplotlib jupyter
```

### 4. Start Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
EDA PART-1.ipynb
```

and run the cells sequentially.

---

## 📌 Project Status

**Completed — EDA Part 1**

This is my first Data Analysis project, focused on understanding an e-commerce dataset through exploratory data analysis and visualization.

---

## 👨‍💻 Author

**Vinay Baikadi**

GitHub: `Vinaybaikadi8835`

