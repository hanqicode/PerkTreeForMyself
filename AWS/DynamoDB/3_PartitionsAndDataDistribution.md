# Partitions and Data Distribution

Link: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/HowItWorks.Partitions.html

## Data Distribution: Partition Key
If your table has a simple primary key(partition key only), DynamoDB stores and retrieves each item based on its partition key value.

Each item's location is determined by the **Hash Value** of its partition key.

We recommend that you choose a partition key that can have a large number of distinct values relative to the number of items in the table.

## Data Distribution: Partition Key and Sort Key
If the table has a composite primary key (partition key and sort key), 
DynamoDB calculates the hash value of the partition key in the same way as described in Data Distribution: Partition Key. 
However, it stores all the items with the same partition key value physically close together, ordered by sort key value.

In a DynamoDB table, there is no upper limit on the number of distinct sort key values per partition key value. 
If you needed to store many billions of Dog items in the Pets table, 
DynamoDB would allocate enough storage to handle this requirement automatically.
