# Olist E-Commerce Analysis

An end-to-end exploratory and statistical analysis of the Olist Brazilian e-commerce dataset, focusing on customer satisfaction, order value, product categories, payment methods, and delivery performance.

## Project Overview

The aim of this project is to explore the factors associated with customer satisfaction in an e-commerce marketplace and translate the analytical findings into meaningful business insights.

The analysis combines descriptive statistics, data visualization, correlation analysis, and hypothesis testing to investigate customer experience from different perspectives.

## Business Questions

The analysis focuses on the following questions:

1. Does customer satisfaction differ significantly across product categories?
2. Does customer satisfaction differ significantly across payment methods?
3. Is delivery duration significantly associated with customer satisfaction?
4. How are order value and basket size distributed?
5. What patterns can be observed in delivery performance and payment behavior?

## Dataset

The Olist dataset consists of multiple relational tables connected through identifiers such as `order_id`, `customer_id`, `product_id`, and `seller_id`.

The analysis uses:

- Customers
- Orders
- Order Items
- Payments
- Reviews
- Products
- Sellers

| Dataset | Rows | Columns |
|---|---:|---:|
| Customers | 99,441 | 5 |
| Order Items | 112,650 | 7 |
| Payments | 103,886 | 5 |
| Reviews | 99,224 | 7 |
| Orders | 99,441 | 8 |
| Products | 32,951 | 9 |
| Sellers | 3,095 | 4 |

The original data contains missing values in selected fields, particularly review comments, order delivery timestamps, and product attributes. Duplicate rows were not detected in the examined datasets.

## Analytical Approach

The project follows an end-to-end analytical workflow:

**Data Preparation → Exploratory Data Analysis → Correlation Analysis → Hypothesis Testing → Visualization → Business Interpretation**

### 1. Data Preparation

The datasets were loaded and examined individually before analysis.

Date fields were converted to appropriate datetime formats, and order-level analytical datasets were created by aggregating information at the appropriate level of analysis.

This approach helps prevent duplicated order records from distorting metrics such as order value, delivery duration, and customer satisfaction.

### 2. Exploratory Data Analysis

The exploratory analysis covers:

- Order value distribution
- Median and average order value
- Basket size and number of items per order
- Freight value
- Delivery duration
- Estimated vs. actual delivery dates
- Payment method distribution
- Product category distribution
- Customer review scores

One notable finding is that approximately 90.1% of orders contain a single item. At the same time, average order value increases substantially as basket size grows, suggesting a potential opportunity to encourage customers to purchase complementary products.

### 3. Correlation Analysis

Relationships between key numerical and ordinal variables were examined, including:

- Order price vs. delivery time
- Order price vs. customer satisfaction
- Product category vs. customer satisfaction
- Payment method vs. customer satisfaction
- Delivery duration vs. customer satisfaction

The analysis distinguishes between correlation and group-based comparisons depending on the type of variables being examined.

### 4. Hypothesis Testing

A significance level of **0.05** was used for the hypothesis tests.

#### Product Category vs. Customer Satisfaction

A one-way ANOVA was used to test whether customer satisfaction differs across product categories.

- **F-statistic:** 13.359
- **p-value:** < 0.001

The null hypothesis was rejected, indicating that customer satisfaction differs significantly across product categories.

The analysis does not identify which specific category pairs differ significantly. Post-hoc pairwise testing would be required for that purpose.

#### Payment Method vs. Customer Satisfaction

A Kruskal-Wallis H test was used to examine differences in customer satisfaction across payment methods.

- **H-statistic:** 14.867
- **p-value:** 0.0019

The null hypothesis was rejected, indicating statistically significant differences in customer satisfaction across payment methods.

However, the average review scores are relatively close, ranging from approximately 4.01 to 4.17. Therefore, the statistical difference appears relatively small in practical terms.

#### Delivery Duration vs. Customer Satisfaction

A Spearman rank correlation test was used to examine the association between delivery duration and customer satisfaction.

- **Correlation coefficient:** -0.235
- **p-value:** < 0.001

The result indicates a statistically significant negative association between delivery duration and customer satisfaction.

The relatively weak correlation suggests that longer delivery times tend to be associated with lower satisfaction, but delivery duration alone does not fully explain differences in customer satisfaction.

## Key Findings

- Customer satisfaction differs significantly across product categories.
- Customer satisfaction also differs significantly across payment methods, although the practical difference between average scores is relatively small.
- Longer delivery durations are associated with lower customer satisfaction.
- The relationship between delivery duration and satisfaction is statistically significant but relatively weak.
- Most orders contain a single item, while larger baskets are associated with substantially higher order values.
- Customer satisfaction should not be explained by a single factor; product characteristics, payment experience, delivery performance, and other factors may jointly influence customer evaluations.

## Business Implications

The findings suggest several potential areas for further business attention:

- Investigate why customer satisfaction varies across product categories.
- Examine the customer experience associated with different payment methods.
- Improve delivery performance where longer delivery durations are observed.
- Encourage larger baskets through complementary product recommendations or cross-selling strategies.
- Combine multiple customer and order characteristics when evaluating customer satisfaction rather than relying on a single metric.

## Limitations

This analysis identifies associations and statistically significant group differences but does not establish causal relationships.

The hypothesis tests show whether statistically significant differences or associations exist, but they do not explain their underlying causes.

In addition, the product category and payment method analyses do not include post-hoc pairwise tests. Therefore, the specific groups responsible for the observed differences cannot be identified.

## Future Work

Potential extensions of this analysis include:

- Applying post-hoc tests for pairwise group comparisons
- Examining additional customer and order characteristics
- Investigating geographic differences in customer satisfaction
- Building predictive models for customer satisfaction
- Developing machine learning models to identify the strongest predictors of customer experience

## Tools & Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Plotly
- SciPy
- Google Colab

## Project Structure

```text
olist-ecommerce-analysis/
│
├── Olist_Ecommerce_Analysis.ipynb
└── README.md
