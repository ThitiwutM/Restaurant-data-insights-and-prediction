# Restaurant-data-insights-and-prediction

This is a term project for the DS512/513/514/515 Data Analytics and Data Science course at SWU, Thailand.

The project aims to explore insights from restaurant sales data and identify the key factors influencing sales volume. In addition, we developed predictive models for quantity sold using linear regression and regularized linear regression techniques (Ridge, Lasso, and Elastic Net) to support restaurants in improving their performance and developing effective strategies to enhance sales.

The process includes data type checking, data cleaning, exploratory data analysis (EDA), data visualization and dashboard creation, feature selection, data pre-processing before modeling, data pipeline development, model building, and model evaluation.

---

โครงงานนี้เป็นโครงงานของรายวิชา DS512/513/514/515 Data Analytics and Data Science ระดับปริญญาโท มหาวิทยาลัยศรีนครินทรวิโรฒ

โครงงานนี้มีวัตถุประสงค์เพื่อสำรวจข้อมูลยอดขายของร้านอาหารและหาปัจจัยสำคัญที่มีผลต่อปริมาณการขาย นอกจากนี้ยังได้พัฒนาโมเดลสำหรับการทำนายปริมาณการขาย (Quantity sold) โดยใช้เทคนิค Linear Regression และ Regularized Linear Regression (Ridge, Lasso และ Elastic Net) เพื่อสนับสนุนร้านอาหารในการปรับปรุงประสิทธิภาพและพัฒนากลยุทธ์ที่เหมาะสมในการเพิ่มยอดขาย

กระบวนการทำงานประกอบด้วย การตรวจสอบประเภทข้อมูล การทำความสะอาดข้อมูล การวิเคราะห์ข้อมูลเบื้องต้น (EDA) การสร้างภาพข้อมูลและแดชบอร์ด การคัดเลือกตัวแปรสำหรับโมเดล การเตรียมข้อมูลก่อนสร้างโมเดล การพัฒนา data pipeline การสร้างโมเดล และการประเมินผลโมเดล

![](https://github.com/ThitiwutM/Restaurant-data-insights-and-prediction/blob/main/project%20framwork.jpg?raw=true)

---

**About Dataset**

The dataset used in this project was obtained from Kaggle, titled “Restaurant Sales Report 2024–2025”, posted by Alexand Chen. 
(https://www.kaggle.com/datasets/alexandchen/restaurant-sales-report-2024-2025?select=restaurant_sales_data.csv) 

Description:

This dataset offers a granular, item-level view of daily sales from a diverse group of 50 restaurants, spanning a full year from January 2024 to January 2025. It serves as a comprehensive resource for time-series analysis, demand forecasting, and investigating the various factors that influence customer purchasing habits across different restaurant types, including Cafes, Casual Dining, Fine Dining, Food Stalls, and Kopitiams.

Each row represents the total quantity sold of a specific menu item at a single restaurant on a given day. The dataset is enriched with valuable contextual information, such as weather conditions, promotions, and special events. It also includes detailed financial metrics for each menu item, including the typical ingredient cost, the observed market price, and the actual selling price, making it ideal for analyzing pricing strategies and promotional effectiveness.

---

**การวิเคราะห์ปัจจัยที่มีผลต่อยอดขายและการทำนายปริมาณการขายของร้านอาหารเพื่อวางแผนกลยุทธ์กระตุ้นยอดขาย**

**1. การวิเคราะห์ปัจจัยที่มีผลต่อยอดขาย**

ปัจจัยที่ส่งผลต่อยอดขาย​: สภาพอากาศแดดให้ยอดขายสูงสุด 298 หน่วย (+13% จากวันฝน) โปรโมชั่นเพิ่มยอดขาย +92% และเหตุการณ์พิเศษเพิ่ม +29% Fine Dining มีกำไรสูงสุด 255 บาท แต่ขายน้อย ขณะที่ Food Stall ขายมาก 311 หน่วย แต่กำไรต่ำ 61 บาท อาหารเช้าขายได้มากกว่าเที่ยง-เย็น 85-119%​

ประสิทธิภาพการกำหนดราคาและโปรโมชั่น​: ราคามีความสัมพันธ์เชิงลบกับยอดขาย (r = -0.54) การให้ส่วนลดเพิ่มยอดขาย +97% แต่ลดกำไรต่อหน่วย -55% โปรโมชั่นเพิ่มยอดขาย +92% แต่ลดกำไรต่อหน่วย -39% (จาก 121 เหลือ 74 บาท) อย่างไรก็ตามกำไรรวมยังเพิ่มขึ้นเนื่องจากปริมาณขายที่สูงขึ้นมาก

![](https://github.com/ThitiwutM/Restaurant-data-insights-and-prediction/blob/main/data%20distribution.jpg?raw=true)

**2. การทำนายปริมาณการขายของร้านอาหาร**

จากการกำหนด Target เป็น quantity_sold และ Features เป็น lag1, actual_selling_price, weather_condition, has_promotion, and special_event

Lasso regression เป็นโมเดลทำนายปริมาณาการขายที่ให้ค่า R2 สูงสุด รวมถึง MAE และ RMSE น้อยที่สุด​ แต่ค่า R2 ที่ได้ยังต่ำ มีค่าเพียง 0.5639

ดังนั้นอาจจะต้องมีการพํนาโมเดลต่อไป โดยมีข้อเสนอแนะดังนี้
- อาจพิจารณาใช้ data ที่เป็น numerical แทน categorical เพื่อความแม่นยำในการทำนาย เช่น อุณหภูมิ ปริมาณฝน และ เปอร์เซ็นต์ส่วนลดค่าอาหาร​
- ใช้การ split data ตามเวลา เนื่องจากข้อมูลเป็น time-series แทน random split​
- พิจารณาโมเดล regression อื่น ๆ ร่วมด้วย เช่น kNN, SVM, และ อื่นๆ​
- พิจารณาใช้การทำนายแบบ regression ร่วมกับการตีความปัจจัยที่ส่งผลต่อยอดขายจากโมเดลด้วย SHAP ​

![](https://github.com/ThitiwutM/Restaurant-data-insights-and-prediction/blob/main/model%20results.jpg?raw=true)
