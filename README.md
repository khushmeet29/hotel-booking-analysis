# Hotel Analytics Data Pipeline - Snowflake

## 🎯 Project Overview
Built a production-ready hotel analytics data pipeline using Snowflake, implementing industry-standard 
Medallion Architecture to transform messy raw booking data into actionable business insights through 
a fully cloud-native solution.

## 📊 Business Problem
The hotel chain had raw, inconsistent booking data with multiple quality issues:
- Invalid email addresses
- Negative pricing amounts
- Incorrect date ranges
- Missing values across critical fields
- Inconsistent status field entries (typos)
- Duplicate records

Management needed quick, accurate insights on:
- Monthly revenue trends
- Booking volume patterns
- Top revenue-generating cities
- Booking type distribution
- Booking status analysis

## 🏗️ Solution Architecture

### Medallion Architecture Implementation

**Bronze Layer (Raw Data Ingestion)**
- Direct ingestion of CSV files from Snowflake Stages
- No transformations - preserving source data exactly as-is
- Audit columns added (load timestamp, source file)

**Silver Layer (Cleaned & Validated Data)**
- Data quality validation and cleansing
- Invalid email correction
- Negative amount handling
- Date range validation
- Status field standardization
- Duplicate removal

**Gold Layer (Business-Ready Analytics)**
- Monthly aggregates (revenue, bookings)
- City-level performance metrics
- Booking type and status summaries
- KPI calculations for dashboard consumption

## 🛠️ Technologies Used
- **Cloud Data Warehouse:** Snowflake
- **Visualization:** Snowsight (native Snowflake dashboards)
- **Data Processing:** SQL
- **Data Ingestion:** Snowflake Stages, File Formats, COPY INTO
- **Architecture Pattern:** Medallion (Bronze-Silver-Gold)

## 📈 Key Features Implemented

### Data Quality Management
- Email validation using regex patterns
- Negative amount detection and handling
- Date range validation (booking dates vs. check-in dates)
- Missing value imputation strategies
- Duplicate record identification and removal
- Status field standardization (typo correction)

### Data Pipeline Automation
- Automated CSV ingestion using Snowflake Stages
- Three-layer transformation logic (Bronze → Silver → Gold)
- Incremental data loading capability
- Error handling and data quality checks

### Business Intelligence Dashboard
- Monthly revenue trends (line chart)
- Monthly bookings volume (line chart)
- Top 5 revenue-generating cities (bar chart)
- Booking type distribution (bar chart)
- Booking status breakdown (bar chart)
- KPI cards: Total Revenue, Total Bookings

## 📊 Dashboard Visualizations

The Snowsight dashboard provides:
- **Revenue Analysis:** Track monthly revenue patterns to identify peak seasons
- **Booking Trends:** Monitor booking volume changes over time
- **Geographic Performance:** Identify top-performing cities for targeted marketing
- **Booking Type Insights:** Understand customer preferences (online vs. phone vs. in-person)
- **Status Monitoring:** Track confirmed, pending, and cancelled bookings

## 🎯 Business Impact & Deliverables
- **Accurate monthly metrics** - Clean data enables reliable trend analysis
- **Correct KPIs** - No data quality issues in final output
- **Easy-to-interpret dashboard** - Management can make quick decisions
- **Automated pipeline** - Reduces manual data processing time
- **Scalable architecture** - Can handle growing data volumes

## 📚 Lessons Learned

**Technical:**
- Medallion Architecture provides clear separation of concerns (raw → clean → business)
- Snowflake's native Snowsight dashboards eliminate need for external BI tools
- SQL-based transformations are powerful for data quality management
- File Formats and Stages simplify data ingestion from external sources

**Business:**
- Data quality directly impacts business decision accuracy
- Standardizing messy fields requires understanding business context
- Visual dashboards must answer specific business questions, not just show data
- Production pipelines need robust error handling and validation

## 🚀 Future Enhancements
- Add incremental loading logic (process only new files)
- Implement DBT for transformation layer documentation
- Add data quality monitoring and alerting
- Create customer segmentation analysis
- Add forecasting models for revenue prediction
- Implement real-time streaming from booking system
