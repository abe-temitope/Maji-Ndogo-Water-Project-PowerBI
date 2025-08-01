# Maji Ndogo Water Services Data Analysis & Transparency Initiative

This repository houses two interconnected Power BI dashboards designed to provide comprehensive insights into the Maji Ndogo water services project. The dashboards aim to empower both strategic decision-makers and the general public with data-driven transparency on project progress, financial allocations, and water access improvements across various regions.

---

## Author Information

**Abe Temitope Moses**

Abe Temitope Moses is a freelance Data and Business Analyst and Scientist, skilled in Excel, SQL, Tableau, and Power BI. He has successfully completed multiple capacity-building programs, including the African Leadership Xcelerator (ALX), the Incubator Hub, and the Power Up Program. With a strong analytical mindset and hands-on project experience, he is passionate about turning data into actionable insights that drive decision-making. Abe is currently open to work opportunities.

**Connect with me:**
* **Twitter:** [iamabetemitope](https://x.com/iamabetemitope)
* **Resume:** [Abe Temitope Moses Resume](https://docs.google.com/document/d/1IfH9cbsfHyQeHlDePQQBiJ5u6Ypvf134dRXRnkhXEUo/edit?usp=drivesdk)
* **LinkedIn:** [abelytics](https://www.linkedin.com/in/abelytics)
* **Facebook:** [Abe Temitope Moses on Facebook](https://www.facebook.com/share/1Weko86iGU/)
* **GitHub:** [abe-temitope](https://github.com/abe-temitope)
* **Portfolio Site:** [Abelytics Portfolio](https://sites.google.com/view/abelytics)

---

## Dashboards Included

This project features two distinct Power BI dashboards:

### 1. Maji Ndogo Stakeholder's Dashboard (For Decision-Makers)

![Stakeholder's Dashboard](Images/Stakeholder%20national.png) "Stakeholder's Dashboard")

This dashboard is tailored for key decision-makers, such as President Aziza Naledi and provincial leaders, providing them with critical data to understand the overall status of water access, identify challenges, and make informed financial and operational decisions.

**Purpose:** To empower national and provincial leaders with accurate, actionable data regarding water access challenges, upgrade requirements, and financial expenditures, facilitating strategic planning and resource allocation.

**Data Sources:** This dashboard primarily leverages the `Md_water_services_data.xlsx` dataset, which includes comprehensive information on water sources, visits, infrastructure costs, and project progress.

**Key Features / Visuals:**
* **Overall Water Access Status:** Summarizes population-related water access on national and provincial levels, distinguishing between rural and urban areas.
* **Water Access Challenges:** Communicates the number of affected people and the types of challenges, potentially hiding less critical sources like `tap_in_homes` for strategic focus.
* **Upgrade Costs & Allocation:** Displays national and provincial budget requirements for upgrades, breaking down costs by province, rural/urban split, and improvement type.
* **High-Impact Summaries:** Includes prominent cards showing total cost of upgrades, current percentage of basic water access, and projected improvement percentages.
* **Interactive Controls:** Features province selectors (slicers) and potentially rural/urban filters to allow decision-makers to focus on relevant data.
* **Dynamic Financial Views (Bookmarks):** Utilizes bookmarks and buttons to toggle between detailed budget tables/visuals per province and per improvement type, optimizing dashboard space.
* **Provincial-Specific Pages:** Designed with the ability to drill down or navigate to dedicated pages for each province, providing localized insights relevant to provincial leaders (e.g., breakdown of budget by town, rural/urban spending, improvements, and relevant provincial data like queues, gender composition, and crime).

**Key Insights:**
* **Strategic Resource Allocation:** Helps leaders understand where funds are most needed (by province, urban/rural, improvement type) to maximize impact on water access.
* **Impact Assessment:** Connects financial investment to tangible improvements in basic water access, allowing for measurement of project success.
* **Targeted Interventions:** Identifies specific water source challenges and affected populations, guiding targeted interventions.
* **Accountability:** Provides a clear overview of financial commitments and their corresponding outputs.

### 2. Maji Ndogo Public Dashboard (For Public Project Monitoring)

![Alt text for the image](path/to/your/image.jpg "Optional title text on hover")

This dashboard focuses on the financial oversight and progress tracking of water improvement projects across Maji Ndogo. It aims to provide transparency to the general public and stakeholders on budgeted vs. actual costs and project completion status.

**Purpose:** To provide a public-facing overview of the financial health and progress of water infrastructure improvement projects, enabling citizens and external stakeholders to monitor spending against budget and track project completion rates over time and by various categories.

**Data Sources:** The dashboard is built upon the `Md_water_services_data(public).xlsx` dataset, specifically utilizing the following tables (or imported CSVs from it):
* `project_progress.csv`: Core project details, completion dates, budgeted and actual costs, and project status.
* `infrastructure_cost.csv`: Standard and rural-adjusted unit costs for different improvement types.
* `location.csv`: Geographic information for towns and regions.
* `vendors.csv`: Details about the vendors involved in projects.

**Key Features / Visuals:**
* **Cumulative Budget & Cost Line Chart:** Tracks the running total of budgeted and actual costs over time, allowing for easy comparison of financial performance.
* **Key Performance Indicator (KPI) Cards:**
    * **Cumulative Budget:** Total allocated budget for completed projects (`$128,450`).
    * **Cumulative Cost:** Total actual expenditure on completed projects (`$131,914.91`).
    * **Difference:** Variance between budgeted and actual costs (reveals if over or under budget).
    * **Total Projects in Backlog:** Count of projects awaiting completion.
    * **Number of Completed Projects:** Count of successfully finished projects.
* **Project Status Bar Chart:** Visualizes the distribution of projects between "Backlog" and "Complete" statuses.
* **Projects by Town/Location Chart:** Shows the number of projects implemented in different towns/regions.
* **Projects by Improvement Type Chart:** Categorizes projects by the type of water infrastructure improvement (e.g., "Drill well", "Install pump").
* **Projects by Vendor Chart:** Displays the number of projects each vendor is associated with.
* **Interactive Slicers:** Date range slicer and Town slicer for dynamic filtering and drilling down into specific periods or locations.

**Key Insights:**
* **Budget vs. Actual Spend:** Provides clear visibility into whether projects are adhering to their allocated budgets or incurring overspends.
* **Project Progress Monitoring:** Allows tracking of projects from backlog to completion, aiding in operational oversight.
* **Geographic Distribution:** Identifies areas with high project activity or specific needs.
* **Resource Allocation:** Insights into which types of improvements are prioritized and which vendors are most active.

**Data Model Highlights:**
* **Dedicated Date Table:** A best practice implemented for robust time intelligence calculations, connected to `project_progress` via `date_of_completion`.
* **Calculated Columns:**
    * `budgeted_improvement_cost`: Dynamically calculates project-specific budgeted costs, accounting for rural adjustments.
    * `Rural_adjusted_cost` (in `infrastructure_cost` table): Adjusts unit costs for rural projects (e.g., `unit_cost_USD * 1.5`).
    * `Aggregated_improvements`: A DAX column to consolidate similar improvement types for clearer visualization (e.g., "Install 1-8 taps" into "Install public tap(s)*")
    * `Average_queue_time` (in `water_source` table): Calculates average queue time per source for basic access classification.
    * `Basic_water_access` (in `water_source` table): Classifies each water source as 'Basic Access' or 'Below Basic Access' based on UN requirements and specific criteria (e.g., clean wells, queue times for shared taps, taps in homes).
* **DAX Measures:** Custom measures for cumulative sums (`cumulative_budget`, `cumulative_cost`), basic water access percentage, and project counts (`Total projects in backlog`, `Number of completed projects`), and cost difference (`Difference`).


**Provinces:**
![Province 1 Page](Images/Province%201.png)
![Province 2 Page](Images/Province%202.png)
![Province 3 Page](Images/Province%203.png)
![Province 4 Page](Images/Province%204.png)
![Province 5 Page](Images/Province%205.png)