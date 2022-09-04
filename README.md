# ArnovaTask

# sales-data

[Download Link](https://github.com/akshay4699/ArnovaTask/raw/main/Visualizattion1.twbx)

# Stock_Google 

 1. Print the highest opening and the lowest closing values of each month for Google.

select month( str_to_date(Date,'%y-%m-%d')) as DateFormat from stocks_google group by DateFormat;
select  month( str_to_date(Date,'%y-%m-%d')) as DateFormat, max(Open), min(Close) from stocks_google group by DateFormat;


# Stock_Netflix

Find the standard deviation of Volume per year for Netflix.

select  year( str_to_date(Date,'%y-%m-%d')) as DateFormat,stddev(Volume) from stocks_netflix group by DateFormat;

# Stock_Amazon and Stock_Apple

select * from stocks_amazon;
select * from stocks_apple;
select (stocks_amazon.Open - stocks_apple.Open) as diff from stocks_amazon join stocks_apple on stocks_amazon.Date = stocks_apple.Date;

# Stock_Amazon

 select * from stocks_amazon;
 select Date,(Open-Close) as diff  from stocks_amazon;
 
 # Stock_Amazon
 
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
