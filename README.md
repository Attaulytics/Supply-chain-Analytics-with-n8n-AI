# 📦 Supply Chain Analytics with AI

This project showcases an automated data analytics workflow for supply chain operations using AI-powered tools and workflow automation. The solution leverages n8n for email integration and data extraction, Supabase for cloud-based PostgreSQL storage, and Quadratic AI for data analysis and KPI generation.
🔗 View in Quadratic (Optional)


# 🧾 Overview

The project extracts emails containing supply chain order data, downloads attachments automatically, stores them in a PostgreSQL database on Supabase, and performs AI-driven data transformation and KPI calculations in Quadratic AI using prompt-based instructions.

# 🛠️ Tools & Technologies Used

n8n – Workflow automation platform for data collection and process automation.

Google Cloud Console – For Gmail OAuth 2.0 authentication.

Supabase – Cloud-based PostgreSQL database for data storage.

Quadratic AI – AI-enhanced spreadsheet environment for prompts and analysis.

OpenExchangeRates API – For retrieving historical foreign exchange rates.


# 🧩 Step-by-Step Workflow

📬 1. Gmail Integration via n8n

Created a project in Google Cloud Console.

Set up Gmail OAuth 2.0 credentials and permissions.

Used n8n to access Gmail inbox and filter by subject line.

Downloaded attachments from filtered emails.

📸 Screenshot: 📸 *Screenshot: Gmail Node Setup in n8n*  




# 🗃️ 2. Supabase Database Setup

Registered on Supabase.

Created a new PostgreSQL database project.

Defined tables based on uploaded CSV schemas.

Used n8n's PostgreSQL integration to upload data to Supabase.

📸 Screenshot: Supabase Table Structure


# 🔗 3. Connect Supabase to Quadratic AI

Connected the Supabase database to Quadratic.

Queried the uploaded tables directly inside the AI spreadsheet.

📸 Screenshot: Data Connection in Quadratic

# ✨ 4. Quadratic AI Prompts Used

### ✅ Prompt 1: Create Date Table
Create a date table that has the dates from 03-01-2025 to 05-31-2025
### ✅ Prompt 2: Create Exchange Rate Table
Use OpenExchangeRates API to generate exchange_rate table for March 1st to May 17th, 2025
### ✅ Prompt 3: Data Cleaning & Merging
Load fact_order_line, dim_products, dim_customers, and exchange_rate
- Clean IDs and remove NULLs
- Convert IDs and dates to correct formats
- Merge using product_id, customer_id, and order date
- Calculate total_amount (USD/INR)
- Drop intermediate columns

### ✅ Prompt 4: KPI Calculation
Generate:
1. Total Order Lines
2. Line Fill Rate = delivery_qty / order_qty
3. Volume Fill Rate
4. Total Orders
5. On-Time Delivery %
6. In-Full Delivery %
7. OTIF (On Time In Full) %

# 📊 Output

A unified fact_summary table with clean and merged data.

All KPIs calculated and displayed using AI prompts.

Exportable format for dashboards and BI tools.

# 🌟 Key Learnings

Built a complete ETL pipeline using low-code tools.

Automated data retrieval and ingestion.

Learned how to use AI to clean and analyze data.

Developed practical understanding of supply chain metrics.

