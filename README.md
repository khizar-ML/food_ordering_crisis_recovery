# Food Ordering Crisis Recovery: Comprehensive Data Analysis & ML Project

## � Developer Information
**Created by:** Khizar abbas Khan  
**Date Started:** January 2026  
**Status:** Active Development  
**Purpose:** Analyzing and controlling damage to brand reputation

---

## ⚠️ IMPORTANT: Dataset Availability

**⚠️ The datasets are NOT included in this repository due to licensing restrictions from CodeBasics.**

To access the same datasets used in this project, visit:
### 🔗 [CodeBasics Resume Project Challenge #23](https://codebasics.io/challenges/codebasics-resume-project-challenge/23)

The challenge page provides:
- Complete datasets for download
- Official problem statement
- Submission guidelines
- Community solutions and discussions

**Quick Setup:**
1. Visit the CodeBasics challenge link above
2. Download the RPC_18 datasets
3. Extract to: `rpc_18_inputs_for_participants/RPC_18_Datasets/`
4. Run the notebooks

---

## �📋 Project Overview

This project is a comprehensive data science and analytics initiative designed to analyze the operational and financial impact of a crisis on a food ordering platform (similar to FoodPanda). The crisis was triggered by negative social media campaigns combined with service delays during the monsoon season. The project aims to quantify the damage, identify root causes, and develop data-driven recovery strategies.

---

## 🎯 Problem Statement

A leading online food ordering platform experienced a significant downturn in business due to:
- **Negative social media campaigns** affecting brand reputation
- **Service delays** caused by monsoon-induced weather conditions
- **Reduced customer confidence** in the delivery ecosystem

**Key Business Challenges:**
- Declining order volumes
- Increased order cancellation rates
- Reduced profit margins
- Loss of delivery partner trust and active participation
- Declining customer sentiment and ratings
- Revenue loss across multiple channels

---

## 🔍 Project Objectives

### Primary Objectives:
1. **Quantify Crisis Impact**
   - Measure total order decline across time periods
   - Calculate cancellation rate trends
   - Analyze revenue loss
   - Track cost implications

2. **Identify Root Causes**
   - Analyze customer acquisition patterns
   - Evaluate delivery partner attrition
   - Assess geographic impact variations
   - Examine delivery performance metrics

3. **Develop Recovery Strategies**
   - Forecast demand recovery scenarios
   - Identify high-potential customer segments
   - Optimize delivery partner allocation
   - Recommend pricing and promotional strategies

4. **Build Predictive Models**
   - Predict order volumes and trends
   - Forecast cancellation rates
   - Identify at-risk customers
   - Estimate recovery timelines

---

## 📊 Dataset Description

### Data Sources
The project uses 8 interconnected datasets from the RPC_18 Competition:

#### Dimension Tables (Reference Data)

**1. `dim_customer.csv`**
- Customer demographic and acquisition information
- Fields: `customer_id`, `city`, `acquisition_channel`, `registration_date`
- Purpose: Analyze customer base composition and acquisition effectiveness

**2. `dim_delivery_partner_.csv`**
- Delivery partner profiles and employment details
- Fields: `delivery_partner_id`, `city`, `vehicle_type`, `employment_type`, `avg_rating`, `is_active`
- Purpose: Track delivery partner availability and performance

**3. `dim_menu_item.csv`**
- Restaurant menu and pricing information
- Fields: `menu_item_id`, `restaurant_id`, `price`, `category`
- Purpose: Understand product portfolio and pricing dynamics

**4. `dim_restaurant.csv`**
- Restaurant master data and operational details
- Fields: `restaurant_id`, `city`, `cuisine_type`, `is_active`
- Purpose: Analyze restaurant network health

#### Fact Tables (Transactional Data)

**5. `fact_orders.csv`**
- Core order transaction data
- Fields: `order_id`, `customer_id`, `restaurant_id`, `delivery_partner_id`, `order_timestamp`, `order_value`, `is_cancelled`
- **Critical for:** Measuring order volumes, cancellation rates, and revenue impact

**6. `fact_order_items.csv`**
- Item-level details within each order
- Fields: `order_id`, `menu_item_id`, `quantity`, `item_price`
- **Critical for:** Analyzing product mix and order composition

**7. `fact_delivery_performance.csv`**
- Delivery operation metrics and service levels
- Fields: `delivery_id`, `order_id`, `delivery_partner_id`, `delivery_time`, `on_time`, `distance`, `delay_reason`
- **Critical for:** Identifying delivery performance issues and weather impact

**8. `fact_ratings.csv`**
- Customer satisfaction feedback and sentiment
- Fields: `rating_id`, `order_id`, `customer_id`, `rating`, `sentiment_score`, `review_text`
- **Critical for:** Understanding customer perception and satisfaction trends

---

## 🏗️ Project Structure

```
FoodOrderingCrisisRecovery/
├── README.md                                    # This file
├── metadata.txt                                 # Data dictionary
├── basic_exploration.ipynb                      # EDA and data understanding
├── primary_business_questions.ipynb             # Crisis impact analysis
├── rpc_18_inputs_for_participants/
│   └── RPC_18_Datasets/
│       ├── dim_customer.csv
│       ├── dim_delivery_partner_.csv
│       ├── dim_menu_item.csv
│       ├── dim_restaurant.csv
│       ├── fact_delivery_performance.csv
│       ├── fact_order_items.csv
│       ├── fact_orders.csv
│       └── fact_ratings.csv
└── RPC_18_Problem_Statement.pdf                 # Official problem statement
```

---

## 📈 Analysis Roadmap

### Phase 1: Exploratory Data Analysis (EDA)
**Notebook:** `basic_exploration.ipynb`

**Key Activities:**
- Load and inspect all datasets
- Identify data quality issues and missing values
- Explore data distributions and patterns
- Understand customer base composition
- Analyze delivery partner network
- Examine restaurant and menu item portfolio
- Initial visualization of key metrics

**Outputs:**
- Data quality report
- Statistical summaries
- Preliminary visualizations
- Data cleaning requirements identified

---

### Phase 2: Crisis Impact Assessment
**Notebook:** `primary_business_questions.ipynb`

**Core Business Questions Addressed:**

1. **Order Volume Impact**
   - Total orders by month (pre-crisis vs. crisis periods)
   - Month-over-month growth trends
   - Order trend visualization with percentage changes

2. **Cancellation Analysis**
   - Order cancellation rate by month
   - Cancellation trends over time
   - Identification of peak crisis periods

3. **Revenue Impact**
   - Total revenue generated (pre-crisis vs. crisis)
   - Average order value trends
   - Revenue loss quantification

4. **Cost Analysis**
   - Cost of cancelled orders
   - Delivery cost implications
   - Margin compression analysis

5. **Temporal Patterns**
   - Peak order hours analysis
   - Seasonal trends
   - Weather/monsoon correlation

**Key Metrics Calculated:**
```python
# Monthly aggregations
- Total orders (Successful + Cancelled)
- Order trend (Month-over-Month % change)
- Cancellation percentage
- Revenue metrics
- Cost structure
```

---

### Phase 3: Stakeholder-Specific Analysis (In Progress)

#### Customer Analysis
- City-wise customer acquisition patterns
- Customer acquisition channel effectiveness
- Customer retention rate decline
- Churn risk identification

#### Delivery Partner Analysis
- Active vs. inactive delivery partner count
- Geographic distribution gaps
- Vehicle type utilization
- Employment type impact
- Rating and performance correlation
- Attrition by city and vehicle type

#### Restaurant Network Analysis
- Active restaurant count trends
- Restaurant performance by cuisine type
- Geographic coverage assessment
- Revenue contribution by restaurant

#### Service Quality Analysis
- Delivery time and on-time percentage
- Impact of weather on delivery performance
- Customer satisfaction (ratings and sentiment)
- Sentiment score trends

---

### Phase 4: Predictive Modeling (Upcoming)

**Model 1: Order Volume Forecasting**
- Time series forecasting (ARIMA, Prophet, LSTM)
- Predict future order volumes
- Recovery timeline estimation

**Model 2: Cancellation Rate Prediction**
- Classification model to predict order cancellation
- Feature engineering from transaction history
- Identify high-risk orders

**Model 3: Customer Churn Prediction**
- Predict customers likely to abandon platform
- Segment customers by retention risk
- Target for retention campaigns

**Model 4: Delivery Performance Optimization**
- Predict delivery time based on context factors
- Optimize delivery partner assignment
- Weather-based demand forecasting

**Model 5: Sentiment Analysis**
- NLP on customer reviews
- Trend analysis of customer perception
- Early warning system for reputation issues

---

### Phase 5: Recovery Strategy & Recommendations (Upcoming)

**Strategic Focus Areas:**
1. **Customer Acquisition & Retention**
   - High-performing acquisition channels
   - Targeted retention campaigns
   - Incentive programs for high-churn segments

2. **Delivery Network Optimization**
   - Partner recruitment strategy
   - Incentive structure improvements
   - Geographic resource allocation

3. **Operational Excellence**
   - Service quality improvement targets
   - Weather-resilience planning
   - Delivery time optimization

4. **Reputation Management**
   - Sentiment-driven intervention strategies
   - Customer satisfaction improvement initiatives
   - Communication strategy

5. **Financial Recovery**
   - Pricing optimization
   - Promotional budget allocation
   - Cost structure optimization

---

## 🛠️ Installation & Setup

### Prerequisites
- Python 3.8 or higher
- Jupyter Notebook or JupyterLab
- Git (optional)

### Required Libraries
```bash
pip install pandas numpy matplotlib seaborn scikit-learn scipy
pip install jupyter notebook
```

### Advanced Analysis Libraries (For upcoming phases)
```bash
pip install statsmodels  # Time series analysis
pip install prophet      # Forecasting
pip install tensorflow   # Deep learning
pip install nltk textblob  # NLP
pip install xgboost lightgbm  # Advanced ML models
```

### Setup Instructions
1. Clone or download the project folder
2. Navigate to the project directory
3. Install required dependencies
4. Place CSV files in `rpc_18_inputs_for_participants/RPC_18_Datasets/` directory
5. Open Jupyter Notebook: `jupyter notebook`
6. Run notebooks in order:
   - Start with `basic_exploration.ipynb`
   - Then `primary_business_questions.ipynb`

---

## 📌 Key Findings (Current Phase)

### Crisis Impact Summary
From the primary business questions analysis:

- **Order Volume Decline**: Significant decrease in total orders from pre-crisis to crisis period
- **High Cancellation Rates**: Cancellation percentage increased during crisis months
- **Revenue Impact**: Direct revenue loss from failed orders plus margin compression
- **Timing Pattern**: Crisis intensified during monsoon months (specific to weather)

### Geographic Insights
- High-traffic cities (Delhi, Bangalore) show proportionally low delivery partner availability
- Delivery partner attrition higher in lower-traffic cities
- Regional customer satisfaction varies significantly

### Operational Insights
- Customer sentiment and ratings degraded during crisis period
- Delivery partner network became strained
- Service quality metrics declined

---

## 📊 Visualization Examples

The project includes comprehensive visualizations:

1. **Order Trend Analysis**
   - Line chart showing total orders with month-over-month growth percentages
   - Color-coded annotations (green for growth, red for decline)

2. **Cancellation Rate Trends**
   - Time series showing cancellation percentage evolution

3. **Geographic Heatmaps**
   - City-wise customer and delivery partner distribution
   - Active vs. inactive breakdown

4. **Customer Segment Analysis**
   - Acquisition channel effectiveness
   - City-wise composition

5. **Delivery Partner Metrics**
   - Rating distribution analysis
   - Employment type and vehicle type breakdown
   - Activity status correlation

6. **Sentiment & Ratings**
   - Distribution of customer ratings
   - Sentiment score trends
   - Perception change over time

---

## 🔄 Workflow & Best Practices

### Data Processing Pipeline
```
Raw Data → Validation → Cleaning → Transformation → Feature Engineering → Analysis
```

### Analysis Methodology
1. **Exploratory**: Understand data characteristics
2. **Descriptive**: Summarize current state (crisis impact)
3. **Diagnostic**: Identify root causes
4. **Predictive**: Forecast future scenarios
5. **Prescriptive**: Recommend actions

### Code Quality Standards
- Functions for reusable code (e.g., `load_data()`, `count_plot()`)
- Clear variable naming conventions
- Documentation in markdown cells
- Commented complex logic

---

## 🎓 Learning Outcomes

By completing this project, you'll gain expertise in:

**Data Analysis:**
- Multi-table data integration and joins
- Time series analysis
- Statistical hypothesis testing
- Business metrics calculation

**Data Science:**
- EDA best practices
- Data visualization techniques
- Feature engineering
- Model selection and evaluation

**Business Acumen:**
- Key performance indicators (KPIs)
- Crisis impact assessment
- Stakeholder communication
- Strategic recommendation development

---

## 📚 Useful Resources

- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [Seaborn Visualization Guide](https://seaborn.pydata.org/)
- [Scikit-learn ML Guide](https://scikit-learn.org/stable/)
- [Time Series Forecasting with Python](https://machinelearningmastery.com/)
- [Customer Analytics Best Practices](https://www.kaggle.com/)

---

## 🚀 Next Steps

1. **Complete Phase 3**: Geographic and segment-specific analysis
2. **Develop Phase 4**: Build predictive models
3. **Implement Phase 5**: Create actionable recovery recommendations
4. **Dashboard Creation**: Build interactive Tableau/Power BI dashboard
5. **Deployment**: Create production-ready scripts for continuous monitoring

---

## 📞 Contact & Questions

For questions, suggestions, or improvements to this analysis, refer to the project documentation or associated problem statement.

---

## 📄 License

This project is part of the RPC_18 Competition data science challenge.

---

## 🙏 Acknowledgments

- **Dataset Source**: [CodeBasics - Resume Project Challenge #23](https://codebasics.io/challenges/codebasics-resume-project-challenge/23)
- **Challenge**: RPC_18 Competition
- **Analysis Framework**: Python Data Science Stack (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn)
- **Context**: Real-world food delivery platform crisis scenario
- **Community**: CodeBasics learning platform

---

## 📄 License & Data Usage

**This repository contains analysis code and documentation only. The datasets used in this project are owned by CodeBasics and are available through their Resume Project Challenge platform.**

Please refer to [CodeBasics terms of service](https://codebasics.io/) for proper data usage and attribution.

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.1 | Jan 2026 | Added developer info and dataset availability notice |
| 1.0 | Jan 2026 | Initial README with complete project structure and analysis roadmap |

---

**Last Updated:** January 28, 2026  
**Project Status:** In Progress (Phase 2-3 completed, Phase 4-5 upcoming)  
**Dataset Source:** [CodeBasics RPC_18 Challenge](https://codebasics.io/challenges/codebasics-resume-project-challenge/23)
