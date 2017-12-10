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

#It's a func() within a func()…The innermost func is evaluated first, then the func that encapsulates it comes later.
```
 - > Q1. In the accounts table, there is a column holding the website for each company. The last three digits specify what type of web address they are using. A list of extensions (and pricing) is provided here. Pull these extensions and provide how many of each website type exist in the accounts table.
```
SELECT right(website, 3) "type", count(*)
FROM accounts
GROUP BY "type" 
```
 - > Q2. There is much debate about how much the name (or even the first letter of a company name) matters. Use the accounts table to pull the first letter of each company name to see the distribution of company names that begin with each letter (or number). 
```
SELECT left(upper(name), 1) "letter", count(*)
FROM accounts
GROUP BY "letter" 
ORDER BY 2 DESC 
```
 - > Q3. Use the accounts table and a CASE statement to create two groups: one group of company names that start with a number and a second group of those company names that start with a letter. What proportion of company names start with a letter?
```
SELECT SUM("num") "nums", SUM("letter") "letters"
FROM 
(SELECT name, CASE WHEN LEFT(UPPER(name), 1) IN ('0','1','2','3','4','5','6','7','8','9') THEN 1 ELSE 0 END AS "num", CASE WHEN LEFT(UPPER(name), 1) IN ('0','1','2','3','4','5','6','7','8','9') THEN 0 ELSE 1 END AS "letter" 
FROM accounts) table_1
```
 - > Q4. Consider vowels as a, e, i, o, and u. What proportion of company names start with a vowel, and what percent start with anything else?
```
SELECT SUM("vow") "vowels", SUM("other") "others"
FROM 
(SELECT name, CASE WHEN LEFT(UPPER(name), 1) IN ('A','E','I','O','U') THEN 1 ELSE 0 END AS "vow", CASE WHEN LEFT(UPPER(name), 1) IN ('A','E','I','O','U') THEN 0 ELSE 1 END AS "other" 
FROM accounts) table_2
```
























