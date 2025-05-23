# 📊 Arnowa Task

## 📁 Project Overview

This project involves **sales data visualization** and **SQL-based stock analysis**. The visualizations are created using **Tableau**, and multiple SQL queries are used to extract insights from various company stock datasets.

---

## 📈 Tableau Visualizations

🔗 **Download Tableau File**: [Click here to download `.twbx`](https://github.com/akshay4699/ArnovaTask/raw/main/Visualizattion1.twbx)

### 1. Total Revenue Generated (By Country)
![Total Revenue By Country](https://user-images.githubusercontent.com/112402869/188328202-cba4b23c-6bdc-4a73-9d73-97996788dd68.PNG)

### 2. Quarterly Revenue Generated (By Country)
![Quarterly Revenue By Country](https://user-images.githubusercontent.com/112402869/188328238-a71c6e6c-3bca-441d-9750-02be2d561343.PNG)

### 3. Total Products Sold
![Total Products Sold](https://user-images.githubusercontent.com/112402869/188328269-9c4e84a4-e02e-4d31-9f84-2b673085fd79.PNG)

### 4. Products Sold (By Product Line)
![Products Sold By Product Line](https://user-images.githubusercontent.com/112402869/188328286-de3c9e73-3240-4172-a9a8-c89156e72ed2.PNG)

### 5. Quarterly Revenue (By Product Line)
![Quarterly Revenue By Product Line](https://user-images.githubusercontent.com/112402869/188328297-bd3339a8-d6af-4840-831f-5a4c5ee61fad.PNG)

### 6. Total Revenue (By Product Line)
![Total Revenue By Product Line](https://user-images.githubusercontent.com/112402869/188328313-227ac79e-ef5c-470d-8c94-2bc4e9398885.PNG)

---

## 🧮 SQL Queries

### 1. 📅 Highest Opening & Lowest Closing per Month (Google)

```
SELECT 
  MONTH(STR_TO_DATE(Date, '%y-%m-%d')) AS DateFormat, 
  MAX(Open), 
  MIN(Close) 
FROM stocks_google 
GROUP BY DateFormat;
````

### 2. 📊 Standard Deviation of Volume per Year (Netflix)
```
SELECT  
  YEAR(STR_TO_DATE(Date, '%y-%m-%d')) AS DateFormat, 
  STDDEV(Volume) 
FROM stocks_netflix 
GROUP BY DateFormat;
```

### 3. 📉 Opening Value Difference (Amazon vs Apple)

```
SELECT 
  (a.Open - b.Open) AS diff 
FROM 
  stocks_amazon a 
JOIN 
  stocks_apple b 
ON a.Date = b.Date;
```

### 4. 💹 Largest Daily Return (Amazon)

```
SELECT 
  Date, 
  (Close - Open) AS diff 
FROM stocks_amazon 
ORDER BY diff DESC 
LIMIT 1;
```

### 5. 🏆 Company with Highest Opening Value Per Day

```
-- Amazon
SELECT Date, MAX(Open) FROM stocks_amazon GROUP BY Date;

-- Apple
SELECT Date, MAX(Open) FROM stocks_apple GROUP BY Date;

-- Google
SELECT Date, MAX(Open) FROM stocks_google GROUP BY Date;

-- Microsoft
SELECT Date, MAX(Open) FROM stocks_microsoft GROUP BY Date;

-- Netflix
SELECT Date, MAX(Open) FROM stocks_netflix GROUP BY Date;

-- Tesla
SELECT Date, MAX(Open) FROM stocks_tesla GROUP BY Date; ```
