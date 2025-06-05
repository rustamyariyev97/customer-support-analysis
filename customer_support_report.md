# Analysis of the Customer Support Process

## Project Objective
The objective of this project is to identify existing issues in the customer support process and provide suggestions to improve service quality.

## Business Requirements
- Monthly number of customer complaints over the past 6 months.
- Average response time to customer inquiries.
- Evaluation of the support team's performance.

## Analysis of the Current Process
Customer complaints are stored in the `customer_complaints` table, and inquiries are stored in the `support_tickets` table. Both tables include timestamps for complaints and responses.

## SQL Queries

### Monthly number of complaints (for the last 6 months):
```sql
SELECT EXTRACT(MONTH FROM complaint_date) AS month, COUNT(*) AS complaint_count
FROM customer_complaints
WHERE complaint_date >= ADD_MONTHS(SYSDATE, -6)
GROUP BY EXTRACT(MONTH FROM complaint_date)
ORDER BY month;
```

### Average response time (in minutes):
```sql
SELECT AVG(response_time) AS avg_response_time_min
FROM support_tickets;
```

## Analysis Results
- An increase in the number of complaints was observed in May and June.
- The average response time is 35 minutes, while the target is below 30 minutes.

## Recommendations
- Investigate the reasons behind the increase in complaints during May and June.
- Optimize support processes to reduce response time.
- Consider adding staff or implementing automation tools during summer months.
