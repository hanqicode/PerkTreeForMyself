# Read Consistency

Link: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.ReadConsistency.html

## Eventually Consistent Reads
DynamoDB may return a response including stale data, for a maximum duration of 20 seconds.

If you repeat your read requests after a short time, the response should return the latest data eventually.

## Strongly Consistent Reads
DynamoDB returns a response with the most up-to-date data.

But it might not be available if there is network delay or outage.

## Default Settings
DynamoDB uses **Eventually Consistent Reads**, unless you specify to use strongly consistent reads.
