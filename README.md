# ArnovaTask

## sales-data

[Download Link](https://github.com/akshay4699/ArnovaTask/raw/main/Visualizattion1.twbx)

   1. Total Revenue Generated (By Country)
   ![c1](https://user-images.githubusercontent.com/112402869/188328202-cba4b23c-6bdc-4a73-9d73-97996788dd68.PNG)

   
   2. Quarterly Revenue Generated (By Country)
   ![c2](https://user-images.githubusercontent.com/112402869/188328238-a71c6e6c-3bca-441d-9750-02be2d561343.PNG)

   3. Total Products Sold
   ![c3](https://user-images.githubusercontent.com/112402869/188328269-9c4e84a4-e02e-4d31-9f84-2b673085fd79.PNG)

   
   4. Total Products Sold (By Product Line)
   ![c4](https://user-images.githubusercontent.com/112402869/188328286-de3c9e73-3240-4172-a9a8-c89156e72ed2.PNG)

   5. Quarterly Revenue (By Product Line)
   ![c5](https://user-images.githubusercontent.com/112402869/188328297-bd3339a8-d6af-4840-831f-5a4c5ee61fad.PNG)

   6. Total Revenue (By Product Line)
   ![c6](https://user-images.githubusercontent.com/112402869/188328313-227ac79e-ef5c-470d-8c94-2bc4e9398885.PNG)

 
## 1. Print the highest opening and the lowest closing values of each month for Google.(Stock_Google)

select month( str_to_date(Date,'%y-%m-%d')) as DateFormat from stocks_google group by DateFormat;
select  month( str_to_date(Date,'%y-%m-%d')) as DateFormat, max(Open), min(Close) from stocks_google group by DateFormat;


##   2. Find the standard deviation of Volume per year for Netflix. (Stock_Netflix)

select  year( str_to_date(Date,'%y-%m-%d')) as DateFormat,stddev(Volume) from stocks_netflix group by DateFormat;

## 3. Find the difference between the opening values of Amazon and Apple. (Stock_Amazon and Stock_Apple)

select * from stocks_amazon;
select * from stocks_apple;
select (stocks_amazon.Open - stocks_apple.Open) as diff from stocks_amazon join stocks_apple on stocks_amazon.Date = stocks_apple.Date;

##  4. Find the largest daily return for Amazon. (Daily return is
calculated by subtracting the opening price from the closing price) (Stock_Amazon)

 select * from stocks_amazon;
 select Date,(Open-Close) as diff  from stocks_amazon;
 
 ## 5. Print the company name with the highest opening value for each day. (Stock_Amazon)
 
  select Date, max(Open) from stocks_amazon group by Date;
 select Date, max(Open) from stocks_apple group by Date;
 select Date, max(Open) from stocks_google group by Date;
 select Date, max(Open) from stocks_microsoft group by Date;
 select Date, max(Open) from stocks_netflix group by Date;
 select Date, max(Open) from stocks_tesla group by Date;
 
 select date_format(now());
 select month(curdate());
 select curdate();
 select * from stocks_amazon;
