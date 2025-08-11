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

![alt text](https://github.com/FishCake9918/MDX_query/blob/main/ConstellationSchema.jpg)



# Executive Summary

### Overview of Findings

The project’s analysis uncovered three major trends across sales, operations, and marketing. Online ticket sales remain the dominant revenue channel but have shown notable declines in recent years, suggesting the need for stronger digital engagement strategies. Operationally, promotion readiness among first officers varies significantly, highlighting opportunities to optimize crew training and career progression planning. From a marketing perspective, high-performing seasonal promotions—especially those with strong point-redemption rates—should be maintained or expanded, while underperforming campaigns require strategic adjustments to improve customer participation.


# Insights Deep Dive
### Ticket Sales Channels:

* **Online channels lead but are declining** – Platforms like Agoda, Traveloka, and the Vietnam Airlines app still produce more total revenue than offline channels but have seen sharp drops (e.g., Traveloka -60%, Agoda -32%, VN Airlines App -27%).
  
* **Offline channels show selective growth** – Certain agencies, such as BenThanh Tourist (+32%) and Fiditour Q5 (+213%), recorded significant revenue gains, though their total sales remain lower than major online platforms.
  
* **Customer behavior may be shifting** – Declines in online revenue and growth in some offline sales suggest changes in customer trust, pricing perception, or promotional appeal.
  
* **Opportunity to revitalize online sales** The higher revenue base of online channels means targeted improvements in digital pricing, promotions, and user experience could yield substantial gains.

<img width="887" height="476" alt="image" src="https://github.com/user-attachments/assets/c72e9147-dd5e-47a9-83f2-70f90de0ea70" />



### Pilot Promotion Criteria:

* **Experience and flight-hour requirements vary widely** – Some first officers meet both the 1,500+ flight-hour requirement and the minimum 3 years of continuous service, while others fall short due to gaps in flying or insufficient total hours.
  
* **Consistency matters as much as totals** – Officers with high total hours but missing a full year of activity (e.g., no flights in 2022) do not meet promotion eligibility, highlighting the importance of steady operational engagement.
  
* **Aircraft-specific experience is critical** – Performance and eligibility are evaluated not only on total flight hours but also on experience with specific aircraft types, aligning promotions with operational needs.
  
* **Data-driven career planning opportunity** – Tracking hours and service continuity can help forecast promotion readiness, enabling more proactive training schedules and succession planning for captains.

<img width="726" height="554" alt="image" src="https://github.com/user-attachments/assets/49e32f73-1624-48a1-b442-3403d9a458cc" />



### Promotional Program Effectiveness:

* **High-performing seasonal campaigns** – Certain summer–autumn promotions, such as Thu An Lành and Mùa thu lãng mạn, achieved strong engagement with redemption rates around 80% and acceptable male participation (~61%), making them prime candidates for continuation.
  
* **Low-redemption programs underperform** – Campaigns with redemption rates below 60% and limited operational history (e.g., launched only in 2024) showed weak customer response and may not warrant further investment.
  
* **Gender participation patterns** – Male participation rates varied across campaigns, suggesting opportunities to tailor promotional benefits or marketing channels to better engage specific customer segments.
  
* **Points-based incentive success** – Programs with competitive discount rates and easy point redemption attracted higher usage, indicating that simple, valuable rewards drive better customer action.

<img width="560" height="569" alt="image" src="https://github.com/user-attachments/assets/e85cee2a-79bb-4cc7-9458-ca99f2353533" />





# Recommendations:

Based on the insights and findings above, we would recommend the Vietnam Airlines to consider the following: 

* Strengthen online sales channels with competitive pricing, seasonal offers, and enhanced booking experiences.**
  
* Support and expand high-performing offline agencies while addressing underperformers.**
  
* Use data-driven tracking to plan pilot promotions, ensuring flight-hour and experience requirements are met.**
  
* Continue top-performing seasonal promotions and redesign or retire low-impact campaigns.**
  


# Assumptions and Caveats:

Throughout the analysis, multiple assumptions were made to manage challenges with the data. These assumptions and caveats are noted below:

* AI-generated dataset – All data is synthetic and does not reflect real Vietnam Airlines operations; patterns and insights are illustrative only.
  
* Analysis was limited to the years 2022–2024, assuming stable market conditions and no major external disruptions.
  
* Criteria such as pilot promotion requirements were applied uniformly, without exceptions for special cases (e.g., medical leave, training programs).
