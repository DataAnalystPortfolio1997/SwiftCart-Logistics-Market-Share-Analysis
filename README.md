**SwiftCart is a mid-sized e-commerce retailer specializing in electronics, apparel, and home goods. Over the last two quarters, the Chief Operating Officer (COO) has noticed a worrying trend: while website traffic is up, revenue growth has stagnated, and logistics costs are rising faster than sales.
The COO suspects that inefficient shipping, regional market share loss, and a lack of customer segmentation are holding the company back. They have no time to dig through raw CSV files; they need a single Power BI dashboard to diagnose these problems immediately.**

[Data link](https://docs.google.com/spreadsheets/d/1SrnmbBawthj1UmUEIPUf1CEcY_NS-DB7/edit?usp=drive_link&ouid=104791159130726046761&rtpof=true&sd=true)

**I made this project in 4 platforms:**
1. Excel (power query, pivot table, DAX measures, excel functions)
2. PL/SQL
3. Python (numpy, pandas)
4. Power BI (charts, DAX measures)

**Data cleaning, duplicate removal, and other processes were performed in PowerQuery on the original dataset. All programs use the pre-processed dataset.**

**Conclusions drawn from the data analysis:**
1. Profit margin for the company = 12.47% .
2. "Standard Class" ship mode has highest average of delivery time and highest standart deviation of delivery time = [41.85 , 62.48] .
3. "Technology" product category has highest return rate = 8.45% .	
4. "South" region has lowest total sales = 391,721.91 .
5. Top 5 products by total revenue : "Canon imageCLASS 2200 Advanced Copier", "Fellowes PB500 Electric Punch Plastic Comb Binding Machine with Manual Bind", "Cisco TelePresence System EX90 Videoconferencing Unit",
   "HON 5400 Series Task Chairs for Big and Tall", "GBC DocuBind TL300 Electric Binding System"
   Bottom 5 products by total profit: "Cubify CubeX 3D Printer Double Head Print", "Lexmark MX611dhe Monochrome Laser Printer", "Cubify CubeX 3D Printer Triple Head Print"
   "Chromcraft Bull-Nose Wood Oval Conference Tables & Bases", "Bush Advantage Collection Racetrack Conference Table" .
6. "July" month has lowest profit rate = 6.21% .
7. "Consumer" segment is most profitable, has highest total sales = 1,161,401.34 and highest profit = 134,119.21, but "Home Office" segment has highest profit rate = 14% .
8. "Central" region has highest average of "days to deliver" = 36.98 . It means that "Central" region is suffering from the worst logistics delay.
9. High discounts are leading to negative profit (losses), correlation between Discount and negative profit rate = 0.825 (This means that there is a strong relationship between these indicators) .
