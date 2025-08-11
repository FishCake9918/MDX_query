# Project Background
This project simulates the design and implementation of a data warehouse and analytical system for an airline, using “Vietnam Airlines” as a sample case to illustrate concepts and workflows.

# Disclaimer
The dataset used in this project is entirely AI-generated for educational purposes. It does not represent real operational data, and the airline name mentioned is used solely as an example with no affiliation to any actual organisation.

Insights and recommendations are provided on the following key areas:

- **Ticket Sales Channels** – Evaluating whether to strengthen online or offline sales channels, based on revenue performance trends. 
- **Pilot Promotion Criteria** – Assessing first officers’ flight hours and experience to determine readiness for promotion to captain.
- **Promotional Program Effectiveness** – Identifying which marketing campaigns deliver the highest engagement and redemption rates, and deciding which to maintain or discontinue. 

The SQL queries used to create database [[Script tạo bảng](https://drive.google.com/file/d/15KicsoV0SDTyikhozqTAB5s99DEjXTME/view?usp=sharing)].

The SQL script used to input dataset [[Dataset](https://docs.google.com/document/d/16_3nBjaKs0Zl643NxnR0GFST8JymyoI-YpiAaZyBSzA/edit?usp=drive_link)]

Targed SQL queries regarding 3 said areas can be found here [[Query](https://drive.google.com/drive/folders/1WQlT06JSSg16G7Wn6KvbS4cXoTANoHoD?usp=drive_link)].

An interactive PowerBI dashboard used to report and explore sales trends can be found here [[Dasboard](https://drive.google.com/file/d/1gWuM41bohYrEFAVXJesJ_5BffaxDSNOI/view?usp=sharing)].


# Data Structure & Initial Checks

The project’s main database structure, shown below, consists of fourteen tables: DIM_THOIGIAN, DIM_KENHBANVE, DIM_TACVU, DIM_PHIHANHDOAN, DIM_KHACHHANG, DIM_MAYBAY, DIM_SANBAY, DIM_TUYENBAY, DIM_KHUYENMAI, DIM_CHUYENBAY, FACT_DATCHO, FACT_CSKH, FACT_THONGTINCHUYENBAY, and FACT_TIEPTHI. A description of each table is as follows:
- **1. DIM_THOIGIAN – Contains date-related attributes from 2022 to 2024 (day, week, month, quarter, year) to enable time-based analysis**
- **2. DIM_KENHBANVE – Stores ticket sales channels and fare classes (e.g., website, app, agents; Economy, Business, First Class) for tracking sales performance by channel and fare type**
- **3. DIM_TACVU – Lists task categories and details for customer service or operational support activities**
- **4. DIM_PHIHANHDOAN – Holds crew member information (name, gender, role, start date, address, birth date, phone number) for managing and analyzing flight crew performance and promotions**
- **5. DIM_KHACHHANG – Stores passenger details (ID, name, gender, nationality, birth date, contact info) for customer analysis**
- **6. DIM_MAYBAY – Records aircraft details (type, manufacturer, seating capacity) to plan fleet utilization and route assignments**
- **7. DIM_SANBAY – Contains airport information (code, name, city, country) for route and network analysis**
- **8. DIM_TUYENBAY – Defines flight routes (origin–destination) for analyzing route performance**
- **9. DIM_KHUYENMAI – Stores promotional campaign details (name, discount rate, points required, start/end dates) for marketing analysis**
- **10. DIM_CHUYENBAY – Contains individual flight details (flight code, aircraft, route, origin/destination airports) for scheduling and performance tracking**
- **11. FACT_DATCHO – Records booking transactions (customer, channel, flight, date, seat, fare, discount, final price) for sales and revenue analysis**
- **12. FACT_CSKH – Logs customer service interactions (customer, flight, date, channel, task, staff member, priority level) for service performance evaluation**
- **13. FACT_THONGTINCHUYENBAY – Tracks operational flight data (crew IDs, time, empty seats, crew flight hours) for performance and resource management**
- **14. FACT_TIEPTHI – Records promotional program participation (customer, campaign, points earned/redeemed, flight, date) for evaluating marketing effectiveness**

[Entity Relationship Diagram here]



# Executive Summary

### Overview of Findings

Explain the overarching findings, trends, and themes in 2-3 sentences here. This section should address the question: "If a stakeholder were to take away 3 main insights from your project, what are the most important things they should know?" You can put yourself in the shoes of a specific stakeholder - for example, a marketing manager or finance director - to think creatively about this section.

[Visualization, including a graph of overall trends or snapshot of a dashboard]



# Insights Deep Dive
### Category 1:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 1]


### Category 2:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 2]


### Category 3:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 3]


### Category 4:

* **Main insight 1.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 2.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 3.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.
  
* **Main insight 4.** More detail about the supporting analysis about this insight, including time frames, quantitative values, and observations about trends.

[Visualization specific to category 4]



# Recommendations:

Based on the insights and findings above, we would recommend the [stakeholder team] to consider the following: 

* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  
* Specific observation that is related to a recommended action. **Recommendation or general guidance based on this observation.**
  


# Assumptions and Caveats:

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

* Assumption 1 (ex: missing country records were for customers based in the US, and were re-coded to be US citizens)
  
* Assumption 1 (ex: data for December 2021 was missing - this was imputed using a combination of historical trends and December 2020 data)
  
* Assumption 1 (ex: because 3% of the refund date column contained non-sensical dates, these were excluded from the analysis)
