# Study-SQL-DataCleaning

## Clean and re-structure messy data.
## Convert columns to different data types.
## Tricks for manipulating NULLs.
*Left( )……beginning???
*Right( )………ending???
*Length( ) 
*POSITION( )
*STRPOS( )
*CONCAT( )
*CAST( )
*COALESCE( ) 

## left( ) / right( ) / length( )
phone_num: 000-000-0000
*LEFT( ) pulls a specified number of characters for each row in a specified column starting at the beginning (or from the left). For example, pull digits of a phone number using: 
*LENGTH( ) provides the number of characters for each row of a specified column. To get the length of each phone number, using: 

>SELECT left(phone_num, 3) area_code, right(phone_num, 8) only_num, right(phone_num, length(phone_num) – 4) alt_num

# func() within a func()…the innermost func is evaluated first, then the func encapsulates it comes later.



