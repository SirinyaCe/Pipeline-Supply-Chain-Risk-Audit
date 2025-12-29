<h1 align="center">Pipeline & Supply Chain Risk Audit</h1>
<h3 align="center"><i>Preventing Infrastructure Failure via SQL & Python Analytics</i></h3>

<div align="center">
  <img src="https://img.shields.io/badge/Python-Pandas-blue?style=for-the-badge&logo=python"/>
  <img src="https://img.shields.io/badge/SQL-SSMS-red?style=for-the-badge&logo=microsoft-sql-server"/>
  <img src="https://img.shields.io/badge/Focus-Risk_Strategy-green?style=for-the-badge"/>
</div>

<br>

<table align="center">
  <tr>
    <td width="1000">
      <h2 align="center">Executive Summary</h2>
      <body>
        <strong>The Business Challenge:</strong> Our infrastructure network faces significant financial exposure due to unforeseen pipeline failures. With a <strong>contractual delay penalty of $50,000 per incident</strong>, the cost of inefficient maintenance logistics is catastrophic.
        <br><br>
        <strong>The Solution:</strong> I engineered an end-to-end audit pipeline using <strong>Python (ETL)</strong> and <strong>SQL (Risk Logic)</strong>. By joining operational sensor data with supply chain logs, I simulated the financial risk of every active shipment to identify "Strategic Conflicts."
      </body>
      <h3>Northstar Metrics (SQL Calculated)</h3>
      <h4>
        <ul>
            <li><strong>Total Failure Exposure ($):</strong> The combined cost of shipping fees plus the probabilistic risk of delay penalties.</li>
            <li><strong>Strategic Misalignment Rate:</strong> The percentage of "Critical" condition pipes assigned to "High-Risk" routes.</li>
            <li><strong>"Double Jeopardy" Events:</strong> Instances where a pipe is about to break AND the replacement part is delayed.</li>
        </ul>
      </h4>
    </td>
  </tr>
</table>

<table align="center">
  <tr>
    <div width="920">
      <h1 align="center">The SQL Audit Results</h1>
      
      <div align="center">
        <img width="900" alt="SQL Audit Results" src="visuals/sql_audit_results.png" />
      </div>
      
      <td width="460" valign="top">
        <h3>1. The "Double Jeopardy" Discovery</h3>
        <ul>
            <li><strong>The Finding:</strong> My SQL audit flagged a massive process failure: <strong>90% of Critical condition pipes</strong> were assigned to <strong>High-Risk shipping routes</strong>.</li>
            <li><strong>The Logic:</strong> I used a <code>CASE WHEN</code> statement to flag every row where <code>Condition = 'Critical'</code> AND <code>Route_Risk = 'High'</code>.</li>
            <li><strong>The Impact:</strong> This exposes the company to a probable <strong>$1M+ in penalties</strong> (20 pipes × $50k) for this batch alone.</li>
        </ul>
      </td>
      
      <td width="460" valign="top">
        <h3>2. Financial Reality Check</h3>
        <ul>
            <li><strong>The "Penny Wise" Trap:</strong> The analysis shows shipping costs (~$200) are negligible compared to the <strong>$50,000 delay penalty</strong>.</li>
            <li><strong>The Variance:</strong> The <em>Total Failure Exposure</em> column hovered consistently around $50,200, proving that shipping carrier choice had almost zero impact on total risk.</li>
            <li><strong>Conclusion:</strong> Optimizing for low shipping costs is a financial error. The risk of the penalty outweighs shipping savings by a factor of <strong>250:1</strong>.</li>
        </ul>
      </td>
    </div>
  </tr>
</table>

<h1 align="center">Strategic Recommendations</h1>

<table align="center">
    <tr>
        <td width="333" valign="top">
            <h3>✅ 1. "Safety First" Protocol</h3>
            <ul>
                <li><strong>Observation:</strong> Critical pipes are currently defaulting to High-Risk carriers.</li>
                <li><strong>Action:</strong> Implement a hard SQL logic rule in the ordering system: <code>IF Condition = 'Critical' THEN Max_Risk = 'Low'</code>.</li>
                <li><strong>Impact:</strong> Eliminates the "Double Jeopardy" risk scenario immediately.</li>
            </ul>
        </td>
        <td width="333" valign="top">
            <h3>✅ 2. Premium Shipping Policy</h3>
            <ul>
                <li><strong>Observation:</strong> The $50k penalty is the dominant cost driver.</li>
                <li><strong>Action:</strong> Automatically upgrade all Critical orders to <strong>Air Freight / Premium Ground</strong>.</li>
                <li><strong>Impact:</strong> Spending an extra $500 on shipping is a negligible "insurance premium" to avoid a $50,000 liability.</li>
            </ul>
        </td>
        <td width="333" valign="top">
            <h3>✅ 3. Short-Haul Audit</h3>
            <ul>
                <li><strong>Observation:</strong> The data showed high risk scores even on short routes (1-3 days lead time).</li>
                <li><strong>Action:</strong> Launch a vendor review for local carriers.</li>
                <li><strong>Impact:</strong> Identify if the risk is due to theft, traffic, or poor handling on short routes.</li>
            </ul>
        </td>
    </tr>
</table>

<br>
