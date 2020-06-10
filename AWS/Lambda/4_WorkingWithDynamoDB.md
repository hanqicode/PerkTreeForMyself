# Working with DynamoDB
Link: https://docs.aws.amazon.com/lambda/latest/dg/with-ddb.html

Lambda reads records from the stream and invokes your function **synchronously** with an event that contains stream records.
Lambda reads records in batches and invokes your function to process records from the batch.

## DynamoDB Streams Event Data Structure
Link: https://docs.aws.amazon.com/lambda/latest/dg/with-ddb.html

For one `record` in `Records`:
```json
{
    "eventID": "89e49439d500adeedecc4a29e8d7bd53",
    "eventName": "INSERT",
    "eventVersion": "1.1",
    "eventSource": "aws:dynamodb",
    "awsRegion": "us-west-2",
    "dynamodb": {
        "ApproximateCreationDateTime": 1571281042,
        "Keys": {
            "SongId": {
                "S": "2"
            }
        },
        "NewImage": {
            "Artist": {
                "S": "Jay"
            },
            "SongId": {
                "S": "2"
            },
            "TTL": {
                "N": "1572280350"
            },
            "Name": {
                "S": "Sky"
            }
        },
        "SequenceNumber": "15000000000005705162256",
        "SizeBytes": 39,
        "StreamViewType": "NEW_AND_OLD_IMAGES"
    },
    "eventSourceARN": "arn:aws:dynamodb:us-west-2:558264035114:table/Songs/stream/2019-10-17T02:12:03.454"
}
```
