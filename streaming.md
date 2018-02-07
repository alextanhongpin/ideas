## How to sync data through ETL batch

- query from source, write into sink. Example, you can stream the query from nodejs and write the data to MySQL. Advantages, flexible query, easy to setup. Disadvantage, not prone to error.
- Use a dedicated solution like Storm, Spark, Apache Beam or Streamsets. There are some learning curve involved, and most of them requires enterprise account for high availability. 
- This sync assumes the state is static - there are no insert 

## What if the query stops?
 The easiest way to recover is to select a time range close to where it stops (or round up to the nearest start of the week/month), from the sink, delete all the data after this time range and from source retrieve all this data from this date. There are some advantages in doing this, as it prevents duplicate key entry. 

## How to know is sync is complete? 
Check the count.

## What do I need to know when syncing data?
Remember to sort it by last update, and not just the row id - the updated date has higher precedence over created date or primary key.

## How to stream data?
Kinesis can deal with data persistence for minimum 24 hours, so it’s a good option. Be careful of concurrently updating data, since the timestamp matters. 

## How to deal with data loss?
Remember to keep a snapshot of the data, and every data streamed must have a timestamp. Start from the last state. 
