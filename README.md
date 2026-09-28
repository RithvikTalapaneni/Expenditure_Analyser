# Expenditure_Analyser
A Python-based financial analytics tool that analyzes messy UPI transactions to uncover spending patterns, top vendors, anomalies, monthly trends, and personalized spending archetypes using Pandas and NumPy.
# SpendDNA 💸

### A Python-based financial analytics tool that decodes your spending patterns.

SpendDNA analyzes six months of Indian bank/UPI transaction data and transforms messy transaction records into meaningful financial insights — including spending categories, vendor patterns, anomalies, monthly trends, and spending personality archetypes.

> **"Spotify Wrapped for your money."**

---

## 📌 Project Overview

SpendDNA was built as part of **Industry-Graded Minor Project**.

The project works with a synthetic transaction dataset representing **Rahul Sharma**, a Bengaluru-based software engineer, and processes raw bank/UPI transaction data using **Python, Pandas, and NumPy**.

The goal is to answer a simple question:

> **Where did all the money go?**

---

## 🚀 Features

### 1. Transaction Parser

* Handles multiple date formats
* Handles ₹, Rs., commas, and decimal amount formats
* Standardizes Debit/Credit transaction types
* Removes duplicate transactions
* Handles invalid/missing values

### 2. Vendor Extraction

Converts messy transaction descriptions into canonical vendor names.

Examples:

* `UPI-SWIGGY-9876@HDFCBANK` → **Swiggy**
* `BUNDL Tech P L` → **Swiggy**
* `GROFERS INDIA P L` → **Blinkit**
* `KIRANAKART TECH` → **Zepto**
* `ANI Technologies` → **Ola**

The extractor identifies **39 canonical vendors** with no uncategorized transactions in the analyzed dataset.

### 3. Spending Category Tagging

Transactions are mapped into meaningful categories such as:

* Food Delivery
* Quick Commerce
* E-commerce
* Transport
* Cafe
* Restaurants
* Subscriptions
* Utilities
* Investments
* Fuel
* Entertainment
* Personal Transfer
* Cash Withdrawal

### 4. Spending Overview

Calculates:

* Total credits
* Total debits
* Net change
* Savings rate
* Top spending categories
* Top vendors
* Transaction count

### 5. Monthly Spending Trends

Creates a category-by-month spending matrix and identifies categories with the largest growth and decline between the beginning and end of the analysis period.

### 6. Time-of-Day Analysis

Analyzes spending across **24 hours of the day** using a NumPy-based category × hour matrix.

This helps identify patterns such as:

* Food spending by time
* Morning cafe activity
* Late-night spending

### 7. Anomaly Detection

Uses **category-level z-scores** to identify unusually large transactions.

A transaction is flagged when:

```text
z-score > 2
```

The analysis identified **41 anomalous transactions** in the dataset.

### 8. Spending Archetypes

SpendDNA applies rule-based financial personality detection.

Possible archetypes include:

* 🍔 The Foodie
* 🛒 The Quick Commerce Junkie
* 🛍️ The Shopaholic
* 📈 The Investor
* 🌙 The Late-Night Snacker
* 🚕 The Cab Commuter
* 📺 The Subscription Lover
* 💸 The YOLO Spender
* 🏦 The Disciplined Saver

The notebook evaluates these archetypes using measurable spending behavior rather than subjective assumptions.

---

## 🛠️ Tech Stack

* **Python**
* **Pandas**
* **NumPy**
* **Jupyter Notebook / Google Colab**

### Project constraints

The project intentionally avoids:

* Regex
* Matplotlib / Seaborn / Plotly
* Scikit-learn
* SciPy
* Statsmodels
* `collections.Counter`
* AI/ML libraries
* Automated profiling libraries
* External transaction datasets

The analysis is built using fundamental Python, Pandas, and NumPy operations.

---

## 📂 Project Structure

```text
SpendDNA/
│
├── SpendDNA_Reference.ipynb
├── rahul_transactions.csv
└── README.md
```

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone <your-repository-link>
cd SpendDNA
```

### 2. Install dependencies

```bash
pip install pandas numpy jupyter
```

### 3. Open the notebook

```bash
jupyter notebook SpendDNA_Reference.ipynb
```

Or upload the notebook and `rahul_transactions.csv` to **Google Colab**.

### 4. Run all cells

Make sure `rahul_transactions.csv` is in the same directory as the notebook.

---

## 📊 Dataset

The project uses a synthetic Indian transaction dataset containing:

* **1,328 raw transactions**
* **18 duplicate rows**
* **1,310 transactions after cleaning**
* **6 months of data**
* **January–June 2024**
* Multiple transaction description formats
* Multiple date and amount formats

The dataset is fictional and is intended only for analytics/project demonstration.

---

## 🔍 Key Technical Concepts

This project demonstrates practical use of:

* Data cleaning
* String manipulation
* Dictionaries and mappings
* Functions
* Conditional logic
* Pandas `groupby`
* Pandas `pivot_table`
* Pandas `.apply()`
* Pandas `.dt`
* NumPy arrays
* Statistical z-score calculation
* Transaction categorization
* Merchant normalization
* Time-based analysis
* Rule-based classification

---

## 💡 Why SpendDNA?

Financial transaction data rarely arrives in a perfectly clean format.

Real-world transaction exports can contain:

* Different date formats
* Different currency formats
* Merchant aliases
* Legal company names instead of consumer-facing brands
* Duplicate records
* P2P transfers
* ATM withdrawals

SpendDNA focuses on solving these data-cleaning and analysis problems before generating meaningful financial insights.

---

## 📈 Sample Output

The notebook produces a terminal-style financial report containing:

```text
================================================
 SpendDNA REPORT - RAHUL SHARMA
 6 months - 1,310 transactions - Jan to Jun 2024
================================================

 EXECUTIVE SUMMARY
 Total credits  : ...
 Total debits   : ...
 Net change     : ...
 Savings rate   : ...

 TOP CATEGORIES
 ...

 TOP VENDORS
 ...

 TIME-OF-DAY PATTERNS
 ...

 TOP ANOMALIES
 ...

 RAHUL'S SPENDING ARCHETYPES
 ...
```

The output is intentionally text-based to comply with the project's visualization constraints.

---

## 🎯 Learning Outcomes

Through this project, I practiced:

1. Cleaning messy financial datasets
2. Building a merchant/vendor normalization system
3. Designing rule-based categorization
4. Performing exploratory transaction analysis
5. Detecting category-level anomalies
6. Extracting time-based spending patterns
7. Building rule-based behavioral archetypes
8. Converting raw transaction data into a readable analytical report

---

## ⚠️ Disclaimer

This project uses **synthetic transaction data** for educational purposes.

No real bank account information or personally identifiable financial data is included in this repository.

---

## 👨‍💻 Author

**Rithvik**

---

## ⭐ If you found this project interesting

Feel free to explore the notebook, experiment with the analysis, and build your own version of SpendDNA using a different transaction dataset.
