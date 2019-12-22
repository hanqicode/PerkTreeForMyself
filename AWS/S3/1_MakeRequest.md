# Making Request
[Developer Doc](https://docs.aws.amazon.com/AmazonS3/latest/dev/AuthUsingAcctOrUserCredJava.html)

To send authenticated requests to Amazon S3 using your AWS account or IAM user credentials, do the following:
1. Use the `AmazonS3ClientBuilder` class to create an `AmazonS3Client` instance.
2. Execute one of the `AmazonS3Client` methods to send requests to Amazon S3.

## Sample
```java
public class MakeRequest {

    private static final String BUCKET_NAME = "qqihan-learn";
    private static final String KEY_NAME = "myfolder/myfile";

    public static void main(String[] args) {
        final AmazonS3 client = AmazonS3ClientBuilder.standard().build();
        final S3Object object = client.getObject(BUCKET_NAME, KEY_NAME);
        System.out.println("Get object: " + object.getKey());
    }
}
```
