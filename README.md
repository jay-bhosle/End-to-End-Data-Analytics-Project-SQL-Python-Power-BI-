🛒 Retail Sales Data Analysis & Forecasting

Sales data for a global electronics retailer, including tables containing information about transactions, products, customers, stores and currency exchange rates.

Analysis done to answer:
What types of products does the company sell, and where are customers located?

Are there any seasonal patterns or trends for order volume or revenue?

How long is the average delivery time in days? Has that changed over time?

Is there a difference in average order value (AOV) for online vs. in-store sales?


End-to-end retail sales data project covering:

SQL database design

Data cleaning & transformation

Data validation

Exploratory Data Analysis (EDA)

Feature engineering

Business insights

Revenue forecasting with Machine Learning

📁 Project Structure
retail-sales-analysis/
│
├── sql/
│   ├── schema.sql
│   ├── cleaning.sql
│   ├── constraints.sql
│
├── notebooks/
│   ├── data_preprocessing.ipynb
│   ├── eda.ipynb
│   ├── modeling.ipynb
│
├── data/
│   ├── customers.csv
│   ├── products.csv
│   ├── sales.csv
│
└── README.md

🧩 Images 1–5: Database Design & SQL Data Cleaning
✅ Database Creation

Created database: sales_analysis

Designed normalized tables:

customers

products

stores

sales

exchange_rates

✅ Data Import

Loaded CSV files using LOAD DATA LOCAL INFILE

Configured:

Field delimiter

Line terminator

Header skipping

✅ Data Cleaning in SQL

Standardized text fields (UPPER, TRIM)

Converted date formats

Removed duplicates

Cleaned price columns

Fixed null values

✅ Data Transformation

Created cleaned tables:

customers_clean

products_clean

sales_clean

stores_clean

✅ Constraints & Relationships

Primary Keys added

Foreign Keys established:

sales → customers

sales → products

sales → stores

Ensured referential integrity.
<img width="1920" height="1080" alt="Screenshot (125)" src="https://github.com/user-attachments/assets/a5d7ce00-97f5-4445-93a7-e97e19d0907d" />
125
<img width="1920" height="1080" alt="Screenshot (127)" src="https://github.com/user-attachments/assets/9a87f4a7-0167-4da4-9077-f6cd079fef80" />
127
<img width="1920" height="1080" alt="Screenshot (128)" src="https://github.com/user-attachments/assets/1a16d4e8-7263-40a2-b925-d28b65b10064" />
128
<img width="1920" height="1080" alt="Screenshot (129)" src="https://github.com/user-attachments/assets/40deace5-fd96-4b24-8b17-7e663babf67c" />
129
<img width="1920" height="1080" alt="Screenshot (130)" src="https://github.com/user-attachments/assets/365f35c0-b564-453d-8e6a-08836962e3e8" />
130

🔍 Images 6–10: Data Validation & Integrity Checks

Performed SQL validation checks:

✔ Null Checks
SELECT * FROM sales_clean WHERE Quantity IS NULL;

✔ Currency Consistency

Verified that currency codes exist in exchange rates.

✔ Store Validation

Ensured no stores have missing square meters.

✔ Exchange Rate Validation

Checked for missing exchange rates.

✔ Duplicate Customers

Validated unique customer IDs.
<img width="1920" height="1080" alt="Screenshot (133)" src="https://github.com/user-attachments/assets/2a8d5514-7fad-4179-ab47-88cb17678ac0" />
133
<img width="1920" height="1080" alt="Screenshot (134)" src="https://github.com/user-attachments/assets/e0abf5ad-99bd-4a81-b826-463d6440a77a" />
134
<img width="1920" height="1080" alt="Screenshot (135)" src="https://github.com/user-attachments/assets/7de2a2fa-8fb4-450a-935d-6e6bf5cfeada" />
135
<img width="1920" height="1080" alt="Screenshot (136)" src="https://github.com/user-attachments/assets/20353a75-953c-4e30-ade7-9c8288e5058c" />
136
<img width="1920" height="1080" alt="Screenshot (137)" src="https://github.com/user-attachments/assets/22263fd0-b76f-4c8a-9460-b45d05f8fed4" />
137

🐍 Images 11–15: Python Setup & Data Preprocessing
🔧 Environment Setup

Installed required packages:

pip install sqlalchemy pymysql pandas matplotlib seaborn scikit-learn

🔗 Database Connection

Used SQLAlchemy to connect:

engine = create_engine("mysql+pymysql://root:password@localhost/sales_analysis")

📥 Data Loading

Loaded cleaned tables:

customers = pd.read_sql("SELECT * FROM customers_clean", engine)
products = pd.read_sql("SELECT * FROM products_clean", engine)
sales = pd.read_sql("SELECT * FROM sales_clean", engine)
stores = pd.read_sql("SELECT * FROM stores_clean", engine)

🧹 Data Cleaning in Python

Standardized column names

Converted dates to datetime

Cleaned currency symbols

Converted price columns to float
<img width="1920" height="1080" alt="Screenshot (138)" src="https://github.com/user-attachments/assets/03755d66-044a-4def-8416-0518b0e7b414" />
138
<img width="1920" height="1080" alt="Screenshot (139)" src="https://github.com/user-attachments/assets/b5208340-aa73-4893-bc51-c24dad7ea752" />
139
<img width="1920" height="1080" alt="Screenshot (140)" src="https://github.com/user-attachments/assets/8d0efb2f-7886-46ac-8f8c-267865ee2b8b" />
140
<img width="1920" height="1080" alt="Screenshot (141)" src="https://github.com/user-attachments/assets/a7424a73-7fa5-4e3f-8e4b-7a683e6d924a" />
141
<img width="1920" height="1080" alt="Screenshot (142)" src="https://github.com/user-attachments/assets/655e36df-1054-4a9c-8bea-9750a85c057f" />
142

📊 Images 16–20: Feature Engineering & EDA
🧮 Feature Engineering

Created:

revenue = quantity × unitprice

deliverydays = deliverydate - orderdate

📈 Summary Statistics

Generated summary metrics for:

Revenue

Quantity

Delivery time

📊 Monthly Revenue Trend

Aggregated revenue by month

Visualized sales trend over time

📌 Category-Level Analysis

Grouped revenue by product category.

🌍 Customer Distribution

Analyzed customers by country.
<img width="1920" height="1080" alt="Screenshot (143)" src="https://github.com/user-attachments/assets/dd7211e0-77ac-4f30-b67e-64fa3aaf4347" />
143
<img width="1920" height="1080" alt="Screenshot (144)" src="https://github.com/user-attachments/assets/e9392b7b-b466-4b50-9617-8c45bcd913e4" />
144
<img width="1920" height="1080" alt="Screenshot (145)" src="https://github.com/user-attachments/assets/4937af2e-9735-4bef-9db4-c84391813f34" />
145
<img width="1920" height="1080" alt="Screenshot (146)" src="https://github.com/user-attachments/assets/90a48dff-a78b-4627-9797-6ec764bc7cdf" />
146
<img width="1920" height="1080" alt="Screenshot (147)" src="https://github.com/user-attachments/assets/1197d1c2-e664-4e75-85c0-b72e2be72b1a" />
147

📈 Images 21–25: Business Insights
🏆 Top Revenue Categories

Identified highest-performing product categories.

🌎 Customer Geography

Countries with highest customer counts:

United States

United Kingdom

Canada

Germany

📅 Seasonality Analysis

Extracted:

Order month

Order year

Observed revenue spikes in specific periods.

🚚 Delivery Performance

Calculated:

Average delivery time

Delivery trends by year

📊 Channel Analysis

Compared:

Online vs In-store revenue
<img width="1920" height="1080" alt="Screenshot (148)" src="https://github.com/user-attachments/assets/0f6f9f34-8a94-42c5-b426-fcac17f01b6c" />
148
<img width="1920" height="1080" alt="Screenshot (149)" src="https://github.com/user-attachments/assets/b15a1748-4c83-464c-83a9-1e56ca05964e" />
149
<img width="1920" height="1080" alt="Screenshot (150)" src="https://github.com/user-attachments/assets/5ebdca50-851e-4ed1-8537-48dac706cd43" />
150
<img width="1920" height="1080" alt="Screenshot (151)" src="https://github.com/user-attachments/assets/9c58e43e-8f8f-4d1d-b32e-47d3e394eeee" />
151
<img width="1920" height="1080" alt="Screenshot (157)" src="https://github.com/user-attachments/assets/88496dcf-e4d1-45eb-ad25-82d5677ac0f8" />
157

🤖 Images 26–30: Modeling & Revenue Forecasting
🎯 Problem

Predict revenue using:

Quantity

Unit Price

Delivery Days

🔄 Data Preparation
X = df[['quantity', 'unitprice', 'deliverydays']]
y = df['revenue']

🧠 Model Used

Linear Regression

model = LinearRegression()
model.fit(X, y)

📊 Output

Extracted coefficients

Interpreted feature importance

📈 Forecasting

Aggregated monthly revenue

Built time-based revenue trend

📌 Key Insights

Revenue strongly correlates with unit price and quantity.

Certain product categories dominate total revenue.

Clear monthly seasonality pattern.

Delivery time has mild impact on revenue.

Online and in-store performance differ significantly.

🛠 Tech Stack

MySQL

SQL

Python

Pandas

Matplotlib

Scikit-Learn

SQLAlchemy

🚀 How to Run
1️⃣ Setup Database

Run SQL scripts:

schema.sql
cleaning.sql
constraints.sql

2️⃣ Install Requirements
pip install -r requirements.txt

3️⃣ Run Notebooks

Execute:

data_preprocessing.ipynb

eda.ipynb

modeling.ipynb

📌 Future Improvements

Add ARIMA/LSTM time series forecasting

Build dashboard (Power BI / Tableau)

Deploy model via API

Add automated ETL pipeline
<img width="1920" height="1080" alt="Screenshot (158)" src="https://github.com/user-attachments/assets/f778343c-ae83-4f26-b6c6-2003c30d9076" />
158
<img width="1920" height="1080" alt="Screenshot (159)" src="https://github.com/user-attachments/assets/ea607dc2-d37a-4e69-8437-72c8a2c1e379" />
159
<img width="1920" height="1080" alt="Screenshot (160)" src="https://github.com/user-attachments/assets/4c0728b5-2ae3-453c-9206-f13148dc940e" />
160
<img width="1920" height="1080" alt="Screenshot (161)" src="https://github.com/user-attachments/assets/307671cd-3197-493c-80b3-82be76cfde9a" />
161
<img width="1920" height="1080" alt="Screenshot (162)" src="https://github.com/user-attachments/assets/032c6b08-34b0-4a26-9a75-71759dfcf725" />
162


























