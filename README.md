# ArnovaTask

# sales-data

[Download Link](https://github.com/akshay4699/ArnovaTask/raw/main/Visualizattion1.twbx)

   1. Total Revenue Generated (By Country)
   ![](c1.PNG)
   
   
   2. Quarterly Revenue Generated (By Country)
   ![](c2.PNG)
   
   3. Total Products Sold
   ![](c3.PNG)
   
   4. Total Products Sold (By Product Line)
   ![](c4.PNG)
   
   5. Quarterly Revenue (By Product Line)
   ![](c5.PNG)
   
   6. Total Revenue (By Product Line)
   ![](c6.PNG)

 
# 1. Print the highest opening and the lowest closing values of each month for Google.(Stock_Google)

select month( str_to_date(Date,'%y-%m-%d')) as DateFormat from stocks_google group by DateFormat;
select  month( str_to_date(Date,'%y-%m-%d')) as DateFormat, max(Open), min(Close) from stocks_google group by DateFormat;


#   2. Find the standard deviation of Volume per year for Netflix. (Stock_Netflix)

Find the standard deviation of Volume per year for Netflix.

select  year( str_to_date(Date,'%y-%m-%d')) as DateFormat,stddev(Volume) from stocks_netflix group by DateFormat;

# 3. Find the difference between the opening values of Amazon and Apple. (Stock_Amazon and Stock_Apple)

select * from stocks_amazon;
select * from stocks_apple;
select (stocks_amazon.Open - stocks_apple.Open) as diff from stocks_amazon join stocks_apple on stocks_amazon.Date = stocks_apple.Date;

#  4. Find the largest daily return for Amazon. (Daily return is
calculated by subtracting the opening price from the closing price) (Stock_Amazon)

 select * from stocks_amazon;
 select Date,(Open-Close) as diff  from stocks_amazon;
 
 # 5. Print the company name with the highest opening value for each day. (Stock_Amazon)
 
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
