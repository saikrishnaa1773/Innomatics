<h1>Project Report: Multi-Source Food Delivery Analytics Pipeline</h1>

<p>
<b>Technical Assessment:</b> Intern Hackathon Submission<br>
<b>Environment:</b> Python 3.x, Google Colab<br>
<b>Primary Objective:</b> Data Harmonization and Consumer Insight Generation
</p>

<h3>Step-by-Step Execution Guide</h3>
<p>Follow these base-level steps to run the analysis:</p>
<ol>
    <li><b>Prepare Files:</b> Ensure you have <code>orders.csv</code>, <code>users.json</code>, and <code>restaurants.sql</code> in your folder.</li>
    <li><b>Setup Environment:</b> Open the provided <code>.ipynb</code> file in Google Colab.</li>
    <li><b>Mount Drive:</b> Run the first cell to connect your Google Drive where the data is stored.</li>
    <li><b>Run Extraction:</b> Execute the Loading cell to bring all three data formats into Python.</li>
    <li><b>Run Cleaning:</b> Execute the Cleaning cell to fix text errors and validate data integrity.</li>
    <li><b>Execute Join:</b> Run the Integration cell to merge all data into one master file.</li>
    <li><b>Generate Insights:</b> Run the final cells to see the graphs and business KPIs.</li>
</ol>

<h3>Data Source Inventory</h3>
<p>The pipeline combines three different data structures into one master analytical file.</p>

<p>
<b>Source Entity:</b> Orders<br>
<b>Format:</b> CSV<br>
<b>Key Mapping:</b> order_id<br>
<b>Attributes:</b> Transaction logs, timestamps, and amounts.
</p>

<p>
<b>Source Entity:</b> User Profiles<br>
<b>Format:</b> JSON<br>
<b>Key Mapping:</b> user_id<br>
<b>Attributes:</b> Geographic data (City) and loyalty status.
</p>

<p>
<b>Source Entity:</b> Restaurants<br>
<b>Format:</b> SQL<br>
<b>Key Mapping:</b> restaurant_id<br>
<b>Attributes:</b> Cuisine classifications and verified ratings.
</p>

<h3>Operational Workflow</h3>

<h4>Stage 1: Extraction and Parsing</h4>
<ul>
    <li>Developed a serverless ingestion method using <b>sqlite3</b> to read relational SQL scripts.</li>
    <li>Used <b>JSON</b> and <b>Pandas</b> libraries to organize semi-structured customer profiles.</li>
</ul>

<h4>Stage 2: Data Quality and Integrity</h4>
<ul>
    <li><b>Domain Validation:</b> Checked that all restaurant ratings are within the range of 1.0 to 5.0.</li>
    <li><b>Normalization:</b> Automated string cleaning and casing standardization for <b>City</b> and <b>Cuisine</b> fields to prevent duplicate filters.</li>
    <li><b>Type Casting:</b> Changed timestamp strings into <b>DateTime</b> objects for reliable time-series data.</li>
</ul>

<h4>Stage 3: Integration Strategy</h4>
<ul>
    <li>Used a <b>Left Join</b> based on the Orders table to keep 100% of the revenue data.</li>
    <li>Fixed schema conflicts where <b>restaurant_name</b> appeared in multiple source files.</li>
</ul>

<h3>Business Intelligence KPIs</h3>
<ul>
    <li><b>Market Share:</b> Revenue and order volume distribution across Tier-1 cities.</li>
    <li><b>Customer Segmentation:</b> Average Order Value (AOV) comparison for <b>Gold</b> and <b>Regular</b> members.</li>
    <li><b>Cuisine Gaps:</b> Mapping popular cuisines against customer satisfaction ratings.</li>
    <li><b>Growth Trends:</b> Monthly tracking of order frequency to assess business growth.</li>
</ul>

<h3>Developer Notes</h3>
<ul>
    <li><b>Scalability:</b> The pipeline is modular; new data batches can be processed by re-running the extraction cell.</li>
    <li><b>Visualization:</b> Used <b>Seaborn</b> for statistical boxplots and <b>Matplotlib</b> for trend lines.</li>
</ul>

<p>
<b>Status:</b> Verified and Complete<br>
<b>Developer:</b> Sai Krishna Anegunta<br>
<b>Date:</b> February 2026
</p>
