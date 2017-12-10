# Study-SQL-DataCleaning

#### 1) Clean and re-structure messy data.
#### 2) Convert columns to different data types.
#### 3) Tricks for manipulating NULLs.
 - *Left( )……beginning???
 - *Right( )………ending???
 - *Length( ) 
 - *POSITION( )
 - *STRPOS( )
 - *CONCAT( )
 - *CAST( )
 - *COALESCE( ) 

<img src="https://user-images.githubusercontent.com/31917400/33804790-61f11248-dda4-11e7-80b3-48be3592c300.png" width="600" height="300" />

### left( ) / right( ) / length( )
phone_num: 000-000-0000
 - *LEFT( ) pulls a specified number of characters for each row in a specified column starting at the beginning (or from the left). For example, pull digits of a phone number using: 
 - *LENGTH( ) provides the number of characters for each row of a specified column. To get the length of each phone number, using: 
```
SELECT LEFT(phone_num, 3) area_code, RIGHT(phone_num, 8) only_num, RIGHT(phone_num, LENGTH(phone_num) – 4) alt_num

#It's a func() within a func()…The innermost func is evaluated first, then the func encapsulates it comes later.
```
 - > Q1. 



