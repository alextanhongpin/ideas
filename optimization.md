## Bulk Delivery

Stream data from the database rather than querying it through pagination - most of the time you will not be able to load the data into memory if you have millions of rows in your table. 

You can choose to stream each row individually, or you can aggregate them and send them in bulk to your message queue. This reduces the number of calls and would be more performant too. Be careful not to exceed the maximum size imposed by your message queue.

Another options is to cluster the data (decision tree) and send them based on what logic to perform.

If you are running a cron task, you can make use of it to perform pagination. So, rather than sending them at a specific time, say 10:00 A.M., you can send them by batch every minute. Just take the number of rows `n_row` divided by the number of times `n` you want to send. For each cron invoked, it will send `n_row / n` items.

Also, use redis to cache the rows of item sent with a sensible key name, preferably containing the date `2017-08-01:24:00:namespace`. 

## Elasticsearch Search Query

Cache the request for performing the search, as it can be reused. Say if you have 1000 rows to be matched, you might only need to call the ElasticSearch 900 times, because 100 of them have similary query params. 
