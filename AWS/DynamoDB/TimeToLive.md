# Time to Live
Link: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/TTL.html

Time to Live (TTL) for Amazon DynamoDB lets you define when items in a table expire 
so that they can be automatically deleted from the database.

## How It Works
TTL compares the current time in **epoch time** format to the time stored in the Time to Live attribute of an item. 
If the epoch time value stored in the attribute is less than the current time, the item is marked as expired and then deleted. 
This processing takes place automatically in the background and does not affect read or write traffic to the table.

### Important
DynamoDB typically deletes expired items within 48 hours of expiration.
It means DynamoDB doesn't delete the item immediately.
