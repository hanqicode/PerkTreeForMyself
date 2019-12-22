# Programmatic Interfaces
Link: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Programming.SDKs.Interfaces.html

There are 3 interfaces when using the AWS SDK in Java.

## Low-Level Interfaces
Link: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Programming.SDKs.Interfaces.LowLevel.html

Sample code:
```java
AmazonDynamoDB client = AmazonDynamoDBClientBuilder.standard().build();

HashMap<String, AttributeValue> key = new HashMap<>();
key.put("Name", new AttributeValue().withS("QiHan"));

GetItemRequest request = new GetItemRequest()
        .withTableName("Friends")
        .withKey(key);

GetItemResult result = client.getItem(request);

AttributeValue age = result.getItem().get("Age");
System.out.println("Age is: " + age.getN());
```

Personally, I don't like to use this way to interact with DDB. 
Because it requires to write a lot of code about querying details, and it is not very clear and clean.

## Document Interfaces
Link: https://docs.aws.amazon.com/amazondynamodb/latest/developerguide/Programming.SDKs.Interfaces.Document.html

Sample code:
```java
AmazonDynamoDB client = AmazonDynamoDBClientBuilder.standard().build();

DynamoDB dynamoDB = new DynamoDB(client);

Table table = dynamoDB.getTable("Friends");

GetItemOutcome outcome = table.getItemOutcome(
        "Name", "QiHan"
);

System.out.println("[Document] Age is: " + outcome.getItem().getInt("Age"));
```

Also, I don't like to use this way. Because it is still too loose to have a clear picture about this record.

## Object Persistence Interface
This allows you to write **object-centric** code rather than **database-centric** code.

Sample code for object:
```java
@Data
@DynamoDBTable(tableName = FriendItem.FRIEND_TABLE_NAME)
public class FriendItem {

    static final String FRIEND_TABLE_NAME = "Friends";
    private static final String HASH_KEY = "Name";
    private static final String ATTRIBUTE_AGE = "Age";

    @DynamoDBHashKey(attributeName = HASH_KEY)
    private String name;

    @DynamoDBAttribute(attributeName = ATTRIBUTE_AGE)
    private int age;
}
```

Note:  
`public` is required. Otherwise, we will see exception:
```
IllegalAccessException: com.amazonaws.services.dynamodbv2.datamodeling.StandardBeanProperties cannot access a member of class xxx with modifiers "public".
```

Sample code for query:
```java
AmazonDynamoDB client = AmazonDynamoDBClientBuilder.standard().build();

DynamoDBMapper mapper = new DynamoDBMapper(client);

FriendItem friendItem = new FriendItem();
friendItem.setName("QiHan");

friendItem = mapper.load(friendItem);

System.out.println("[Object] Age is: " + friendItem.getAge());
```

We can see here: If we ignore the configuration of DDB, it is clear to interact with DDB. 

Just build an object, query, and get attributes from object directly.

So, I would prefer to use this way in development. 
Besides, I need to dive deeper into `DynamoDBMapper` class and read its API documents.
