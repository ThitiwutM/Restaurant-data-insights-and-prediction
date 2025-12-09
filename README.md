# Restaurant-data-insights-and-prediction

This is a term project for the DS512/513/514/515 Data Analytics and Data Science course at SWU, Thailand.

The project aims to explore insights from restaurant sales data and identify the key factors influencing sales volume. In addition, we developed predictive models for quantity sold using linear regression and regularized linear regression techniques (Ridge, Lasso, and Elastic Net) to support restaurants in improving their performance and developing effective strategies to enhance sales.

The process includes data type checking, data cleaning, exploratory data analysis (EDA), data visualization and dashboard creation, feature selection, data pre-processing before modeling, data pipeline development, model building, and model evaluation.

โครงงานนี้เป็นโครงงานของรายวิชา DS512/513/514/515 Data Analytics and Data Science ระดับปริญญาโท มหาวิทยาลัยศรีนครินทรวิโรฒ

โครงงานนี้มีวัตถุประสงค์เพื่อสำรวจข้อมูลยอดขายของร้านอาหารและหาปัจจัยสำคัญที่มีผลต่อปริมาณการขาย นอกจากนี้ยังได้พัฒนาโมเดลสำหรับการทำนายปริมาณการขาย (Quantity sold) โดยใช้เทคนิค Linear Regression และ Regularized Linear Regression (Ridge, Lasso และ Elastic Net) เพื่อสนับสนุนร้านอาหารในการปรับปรุงประสิทธิภาพและพัฒนากลยุทธ์ที่เหมาะสมในการเพิ่มยอดขาย

กระบวนการทำงานประกอบด้วย การตรวจสอบประเภทข้อมูล การทำความสะอาดข้อมูล การวิเคราะห์ข้อมูลเบื้องต้น (EDA) การสร้างภาพข้อมูลและแดชบอร์ด การคัดเลือกตัวแปรสำหรับโมเดล การเตรียมข้อมูลก่อนสร้างโมเดล การพัฒนา data pipeline การสร้างโมเดล และการประเมินผลโมเดล

---

**About Dataset**

The dataset used in this project was obtained from Kaggle, titled “Restaurant Sales Report 2024–2025”, posted by Alexand Chen. 
(https://www.kaggle.com/datasets/alexandchen/restaurant-sales-report-2024-2025?select=restaurant_sales_data.csv) 

Description:

This dataset offers a granular, item-level view of daily sales from a diverse group of 50 restaurants, spanning a full year from January 2024 to January 2025. It serves as a comprehensive resource for time-series analysis, demand forecasting, and investigating the various factors that influence customer purchasing habits across different restaurant types, including Cafes, Casual Dining, Fine Dining, Food Stalls, and Kopitiams.

Each row represents the total quantity sold of a specific menu item at a single restaurant on a given day. The dataset is enriched with valuable contextual information, such as weather conditions, promotions, and special events. It also includes detailed financial metrics for each menu item, including the typical ingredient cost, the observed market price, and the actual selling price, making it ideal for analyzing pricing strategies and promotional effectiveness.
