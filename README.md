🏗️ Construction Project Dashboard
A real-time construction project management dashboard built with pure frontend technology. By connecting directly to Google Sheets, it achieves real-time data visualization and multi-dimensional analysis without the need for any backend servers or databases.

Dashboard Preview

✨ Key Features
Real-Time Sync: Connects directly to Google Sheets. Once sheet data is updated, simply refresh the webpage to sync the dashboard.
Multi-dimensional Data Analysis: Includes 8 core KPI metrics (Total Projects, Contract Value, Paid to Date, Outstanding, Avg Completion, etc.).
Rich Visualizations:
Contract Value by Category (Bar Chart)
Project Status, Risk Level, On-Time Finish Rate (Doughnut Charts)
Paid by Contractor Top 10 (Horizontal Bar Chart)
Monthly Contract Trend (Line Chart)
Top 10 Contractors Data Table
Dynamic Interactive Filtering: Cascading filters by Category, Status, State, and Contractor. All charts and KPIs update in real-time.
Smart Data Parsing: Automatically cleans currency formats (removes $ and ,) and perfectly parses DD/MM/YYYY (Australian/UK) date formats.
Modern UI: Dark theme design with CSS variables, adapts to different screen heights, and includes smooth transitions.
Fallback Mechanism: Automatically provides a local CSV file upload alternative if the Google Sheets connection fails or the network is offline.
🛠️ Tech Stack
HTML5 / CSS3: Native layout and dark mode styling variables.
JavaScript (ES6+): Vanilla JS logic with zero framework dependencies.
Chart.js 4.x: Used for rendering all responsive charts.
PapaParse 5.x: Powerful library for parsing CSV data in the browser.
🚀 Quick Start
1. Prepare Google Sheets Data
Ensure your Google Sheets header row contains the following fields (names must match exactly, case-sensitive):Project ID, Project Name, Client, Contractor, Category, Project Manager, State, City, Start Date, Expected Finish, Actual Finish, Status, Contract Value, Variation Value, Current Contract, Paid to Date, Outstanding, Completion %, Risk Level, Priority, Invoice Count, Last Payment, Contractor Rating

2. Set Sheet Permissions
Click Share in the top right corner of your Google Sheet and set the access to "Anyone with the link" as a "Viewer".

3. Configure the Project
Download the index.html file from this repository, open it with a code editor, and find the configuration block at the top of the <script> tag:

/* ==================== Google Sheets Config ==================== */const SHEET_ID = 'YOUR_SHEET_ID';   // Copy from the sheet URL after /d/const SHEET_NAME = 'Project';       // Your actual sheet tab name// ==============================================================
Finding SHEET_ID: Open your Google Sheet and look at the browser address bar.
The URL usually looks like: https://docs.google.com/spreadsheets/d/[THIS_IS_YOUR_SHEET_ID]/edit
Setting SHEET_NAME: Enter the exact tab name found at the bottom left of your sheet (e.g., Sheet1 or Project).
4. Run
Simply double-click the index.html file to open it in your browser. The dashboard will load your data automatically.

📦 Deployment
Since this is a purely static webpage, you can deploy it easily and for free:

GitHub Pages: Push the code to a GitHub repository, go to Settings -> Pages, select the branch, and generate a live URL.
Vercel / Netlify: Drag and drop the project folder into the Vercel or Netlify deployment dashboard. You will get a live HTTPS domain in seconds.
📂 Project Structure
text

.
├── index.html       # Single-file application containing all HTML, CSS, and JS
└── README.md        # Project documentation
📝 Notes
Data Caching: Google Sheets' CSV export links may have a few minutes of cache delay. If recently updated data doesn't appear immediately, wait a moment or force refresh the browser (Ctrl+F5).
Date Format: This dashboard includes specific logic to parse DD/MM/YYYY formats. If your sheet uses the US MM/DD/YYYY format, you may need to modify the pD() function in the code.
Empty Data Handling: If a row is missing a Project ID, it will be automatically filtered out and not displayed on the dashboard.
📄 License
This project is licensed under the MIT License.
All Rights Reserved
