# 🛡️ Pipeline & Supply Chain Risk Audit
### *Preventing Infrastructure Failure via SQL & Python Analytics*

![Python](https://img.shields.io/badge/Python-3.9-blue?style=for-the-badge&logo=python)
![SQL](https://img.shields.io/badge/SQL_Server-SSMS-red?style=for-the-badge&logo=microsoft-sql-server)
![Data Analysis](https://img.shields.io/badge/Focus-Risk_Audit-green?style=for-the-badge)

## 📌 Executive Summary
**The Business Problem:**
Our infrastructure network faces significant financial exposure due to unforeseen pipeline failures. With a **contractual delay penalty of $50,000 per incident**, the cost of inefficient maintenance logistics is catastrophic. A preliminary review suggested that our most critical repair requests were being routed inefficiently, increasing the risk of downtime.

**The Solution:**
I engineered an end-to-end audit pipeline using **Python (for ETL)** and **SQL (for Logic)** to stress-test our logistics strategy. By joining operational sensor data with supply chain logs, I simulated the financial risk of every active shipment.

**The Impact:**
🚨 **Critical Discovery:** The audit revealed a "Double Jeopardy" scenario—**90% of Critical condition pipes** were assigned to **High-Risk shipping routes**. Correcting this logic gap could prevent an estimated **$1M+ in potential liability** for the current batch alone.

---

## 🛠️ Technical Workflow

| Stage | Tool | Action |
| :--- | :--- | :--- |
| **1. Data Engineering** | `Python (Pandas)` | Cleaned raw sensor logs, standardized headers, and generated relational keys (`route_id`) to bridge the gap between Maintenance and Logistics datasets. |
| **2. Risk Algorithm** | `SQL (SSMS)` | Developed a `CASE WHEN` logic system to flag "Strategic Conflicts" (e.g., Critical Pipe + High Risk Route). |
| **3. Financial Modeling** | `SQL` | Calculated **Total Failure Exposure** by combining fixed shipping costs with probabilistic delay penalties. |

---

## 🔎 The SQL Audit (The "Hero" Query)
I moved beyond simple data retrieval to build a **Strategic Alert System**. This query doesn't just list rows; it evaluates business logic to flag dangerous process failures.

```sql
/* PROJECT: Integrated Risk Audit
   OBJECTIVE: Identify "Strategic Conflicts" in Logistics
   LOGIC: Flag instances where Critical pipes are on High-Risk routes.
*/

SELECT TOP 20
    p.pipe_id,
    p.condition AS pipe_condition,
    s.risk_classification AS route_risk_level,
    
    -- Financial Risk Calculation (Probability * Penalty)
    FORMAT(s.shipping_costs + (s.delay_probability * 50000), 'C', 'en-US') 
    AS total_failure_exposure,

    -- Automated Strategic Alert System
    CASE 
        WHEN p.condition = 'Critical' AND s.risk_classification LIKE 'High%' 
        THEN 'CRITICAL ALERT: Bad Logistics'
        WHEN s.lead_time_days > 20 THEN 'Warning: Slow Route'
        ELSE 'Standard'
    END AS strategic_alert

FROM pipeline_linked p
INNER JOIN supply_chain s ON p.associated_route_id = s.route_id
WHERE p.condition = 'Critical'
ORDER BY s.delay_probability DESC;
