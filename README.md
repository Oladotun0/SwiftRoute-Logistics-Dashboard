# 🚚 SwiftRoute Logistics Analytics Dashboard

**Author:** Ismail Oladotun Lawal  
**Tool:** Microsoft Power BI  
**Data Period:** January 2023 – December 2024  
**Project Type:** Personal Learning Project  

---

## 📌 Project Overview

SwiftRoute is a fictional logistics company operating across **6 delivery hubs in Texas**, managing a fleet of **45 vehicles** and **55 drivers**. This Power BI dashboard was built to give operations and management teams a single, interactive view of the company's performance — covering driver efficiency, hub throughput, and fleet health.

The business problem was straightforward: with nearly **28,000 orders over 2 years**, decision-makers needed a way to quickly identify delays, underperforming assets, and capacity issues without digging through raw spreadsheets.

The solution is a **4-page interactive dashboard** that tracks KPIs in real time, supports month-over-month comparisons, and allows filtering by year, month, and individual driver — all built from 4 CSV data sources loaded into Power BI.

---

## 📂 Data Sources

| Table | Rows | Description |
|-------|------|-------------|
| Orders | 27,979 | Delivery records — dates, status, delay reason, hub, driver, vehicle, satisfaction score, delivery time |
| Drivers | 55 | Driver profiles — employment type, hire date, experience years, performance rating |
| Vehicles | 45 | Fleet inventory — model, status (active/maintenance), breakdown count, vehicle code |
| Hubs | 6 | Hub names and maximum processing capacity |

---

## 🛠️ Tools & Process

- **Microsoft Power BI Desktop** — data modeling, DAX measures, and dashboard design
- **Power Query** — data cleaning (removed blank rows, standardized date formats, corrected data types)
- **DAX** — calculated KPIs including MoM growth, on-time delivery rate, CSAT %, delay rates, and hub efficiency
- **Data Modeling** — Many-to-one relationships linking Orders to Drivers, Vehicles, and Hubs

---

## 📊 Dashboard Pages & Business Requirements

### 1. 🏠 SwiftRoute Overview (Main Dashboard)

The landing page answers the most important business question: *"How are we performing right now compared to last month?"*

**KPIs tracked (with Month-over-Month comparisons):**

| KPI | Purpose |
|-----|---------|
| Total Orders | Monitor order volume and MoM growth/decline |
| On-Time Delivery Rate (%) | Track delivery punctuality and MoM change |
| Customer Satisfaction Score (CSAT %) | Measure customer experience and MoM trend |
| Average Delivery Time (Hours) | Monitor operational speed and MoM change |

**Summary visuals** for Hubs, Drivers, and Vehicles give a quick network-wide snapshot before diving into detail pages.

**Overall performance (2023–2024):**
- Total orders: **27,979** (13,976 in 2023 / 14,003 in 2024)
- On-time delivery rate: **78.9%**
- Overall delay rate: **21.1%** (5,908 delayed orders)
- Average customer satisfaction: **4.17 / 5**
- Average delivery time: **35.8 hours**
- Cancellation rate: **0.9%** (252 orders)

---

### 2. 🧑‍✈️ Drivers Overview

**Business goal:** Identify skill gaps, coaching opportunities, and workload patterns across the driver workforce.

**Key metrics:**
- Total drivers: **55** (47 Full-time | 6 Part-time | 2 Contract)
- Average experience: **4.2 years**
- Average performance rating: **3.58 / 5**

**Visuals & their business use:**

| Visual | Chart Type | Business Use Case |
|--------|-----------|-------------------|
| Number of Drivers | KPI Card | Workforce planning and capacity assessment |
| Experience vs Rating | Scatter Plot | Identify skill gaps and training needs |
| Drivers with Most Delays | Bar Chart | Target coaching at highest-delay drivers |
| Driver Profile Summary | KPI Card | Individual evaluation — hire date, YOE, star rating, monthly deliveries |
| Monthly Trend of Orders | Line Chart | Analyze driver workload patterns and seasonal demand |

**Key insights:**
- Best performer: **Charles Moore** — delay rate of only **17.7%**, avg satisfaction **4.24/5**
- Worst performer: **Lisa Moore** — delay rate of **25.7%**, nearly 8 points above the best
- **Experience does not guarantee performance** — some drivers with 7+ years still rank near the bottom, confirming the business need for targeted coaching rather than just tenure-based assessment
- Rating distribution: 8 drivers rated 5/5 | 22 rated 4/5 | 21 rated 3/5 | only 4 rated below 3

**Top 5 drivers by delay rate:**

| Driver | Total Orders | Delay Rate | Avg Satisfaction |
|--------|-------------|------------|-----------------|
| Lisa Moore | 417 | 25.7% | 4.15 |
| Patricia Martinez | 443 | 24.8% | 4.11 |
| Daniel Garcia | 389 | 24.4% | 4.15 |
| Jennifer Lopez | 404 | 24.0% | 4.07 |
| Linda Williams | 437 | 23.3% | 4.16 |

---

### 3. 🏭 Hubs Overview

**Business goal:** Identify which hubs are operating efficiently, which are over/under capacity, and where processing bottlenecks occur.

**Visuals & their business use:**

| Visual | Chart Type | Business Use Case |
|--------|-----------|-------------------|
| Total Number of Hubs | KPI Card | Network size and coverage visibility |
| Orders Processed vs Hub Capacity | Clustered Column Chart | Identify over/under-utilized hubs for workload redistribution |
| Hub Performance Ranking | Bar Chart | Compare hub efficiency and surface underperformers |
| Hub Order Processing Time | Matrix Chart | Identify slow-processing hubs and improve turnaround time by day |

**Hub performance breakdown:**

| Hub | Total Orders | Delay Rate | Max Capacity |
|-----|-------------|------------|-------------|
| Dallas Main Hub | 7,345 | 21.1% | 250 |
| Houston Hub | 6,875 | 20.9% | 380 |
| Austin Hub | 4,065 | **22.1%** | 220 |
| San Antonio Hub | 3,721 | 21.3% | 200 |
| Fort Worth Hub | 3,255 | 21.5% | 180 |
| El Paso Hub | 2,718 | **19.4%** | 150 |

**Key insights:**
- **El Paso Hub** is the most efficient — lowest delay rate (19.4%) despite being the smallest hub. Its lean processes could be studied and replicated across the network
- **Austin Hub** has the highest delay rate (22.1%) without being the busiest — a red flag for operational or staffing issues that needs investigation
- **Houston Hub** has the most capacity (380) but is not the highest volume hub, suggesting available headroom to absorb orders from overloaded hubs
- Monthly orders are stable year-round, ranging between **1,036 and 1,233 per month** — no major seasonal spikes, making capacity planning more predictable

---

### 4. 🚗 Vehicle Overview

**Business goal:** Monitor fleet availability, identify high-breakdown vehicles, and optimize vehicle utilization across order types.

**Visuals & their business use:**

| Visual | Chart Type | Business Use Case |
|--------|-----------|-------------------|
| Number of Vehicles | KPI Card | Fleet size for capacity planning |
| Active vs Maintenance | Donut Chart | Monitor fleet availability and operational readiness |
| Vehicle Age vs Breakdown | Scatter Chart | Identify aging vehicles with higher maintenance risk |
| Breakdown by Vehicle Code | Bar Chart | Target specific vehicles for maintenance action |
| Breakdown by Vehicle Model | Bar Chart | Evaluate model reliability across the fleet |
| Total Orders by Vehicle Model | Bar Chart | Identify high-utilization models |
| Orders by Vehicle Type | Donut Chart | Understand fleet utilization patterns |

**Fleet health summary:**

| Status | Count | Share |
|--------|-------|-------|
| Active | 33 | 73.3% |
| Under Maintenance | 12 | 26.7% |

**Order distribution by vehicle type:**

| Vehicle Type | Orders | Share |
|-------------|--------|-------|
| Van | 17,480 | 62.5% |
| Truck | 6,531 | 23.3% |
| Pickup | 2,837 | 10.1% |
| Box Truck | 1,131 | 4.0% |

**Top 5 vehicles by breakdown count:**

| Vehicle Model | Breakdowns |
|--------------|-----------|
| Freightliner M2 | 153 |
| Mercedes Sprinter | 92 |
| Ford Transit | 68 |
| Ford F-150 | 46 |
| Ram ProMaster | 44 |

**Key insights:**
- **26.7% of the fleet is under maintenance** at any given time — this directly reduces delivery capacity and contributes to delays
- **Freightliner M2 records 153 breakdowns** — almost double the second-highest model. Urgent fleet review needed; consider replacing or phasing out this model
- **Vans handle 62.5% of all orders** — they are the backbone of operations. Any drop in van availability would have an outsized impact on the entire network
- **Vehicle Breakdown** is one of the top 5 delay causes alongside Road Construction, Package Sorting Errors, Driver Unavailability, and Hub Processing Delays

---

## 💡 Top Business Recommendations

1. **Target the 21.1% delay rate** — with 5,908 delayed orders over 2 years, reducing delays by just 5 percentage points would recover ~1,400 deliveries annually
2. **Investigate Austin Hub** — highest delay rate (22.1%) despite mid-range volume. Could be a staffing, routing, or operational process issue
3. **Review the Freightliner M2 fleet** — 153 breakdowns is abnormally high and directly causes delays. A cost-benefit analysis on replacement vs. repair is needed
4. **Replicate El Paso Hub practices** — the most efficient hub in the network. Understanding what they do differently could lift performance across all 6 hubs
5. **Coach bottom-tier drivers** — the gap between the best (17.7%) and worst (25.7%) delay rate shows that targeted training could meaningfully improve the network average
6. **Leverage Houston Hub's spare capacity** — with the highest capacity (380) but not the highest volume, it can absorb overflow from Dallas and Austin during peak periods

---

## 🎨 Design Decisions

- **Color theme:** Purple (`#6D28D9`) with shades (`#A855F7`, `#4C1D95`, `#C4B5FD`) for a consistent, professional look
- **Navigation:** Page buttons on every page for seamless movement across the report
- **Slicers:** Year and Month on all pages; Driver Name slicer on the Drivers page
- **MoM indicators:** KPI cards on the main dashboard show arrows and percentage change vs. the previous month
- **Driver Profile Card:** Dynamic card that updates automatically based on the selected driver name

---

## 🔧 Skills Demonstrated

- Data ingestion and transformation in **Power Query** (blank row removal, date standardization, type correction)
- **Star schema** data modeling with Many-to-one relationships
- **DAX measures** — Total Orders, MoM Growth %, On-Time Rate, CSAT %, Delay Rate, Avg Delivery Time, Hub Efficiency
- **4-page interactive dashboard** design with consistent theming and navigation
- Visual types used: Scatter charts, Donut charts, Clustered column charts, Bar charts, Area/Line charts, Matrix charts, KPI cards
- **Dynamic Driver Profile Card** updating from slicer selection
- Data storytelling — layout designed to guide the viewer from overview → detail → insight

---

## 📁 Repository Contents

| File | Description |
|------|-------------|
| `SwiftRoute.pbix` | Power BI report file |
| `Orders.csv` | 27,979 order records (2023–2024) |
| `Drivers.csv` | 55 driver profiles |
| `Vehicles.csv` | 45 vehicle records |
| `Hubs.csv` | 6 hub details with capacity |

---

## 🚀 How to View

1. Download `SwiftRoute.pbix`
2. Open with [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
3. Use the page navigation buttons to move between dashboards
4. Use the **Year**, **Month**, and **Driver Name** slicers to filter interactively

---

*Built with 💜 by Ismail Oladotun Lawal | Microsoft Power BI*
