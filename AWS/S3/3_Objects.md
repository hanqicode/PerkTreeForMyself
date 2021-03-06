# Objects
Amazon S3 is a simple key, value store actually. Generally, the value would be files instead of string/integer.

## Terminology
- **Key**: You use the object key to retrieve the object.
- **Version ID**: Within a bucket, a key and version ID uniquely identify an object. The version ID is a string that Amazon S3 generates when you add an object to a bucket.
- **Value**: The content that you are storing.
- **Metadata**: A set of name-value pairs with which you can store information regarding the object.

## Object Key Naming Guidelines
You can use any UTF-8 character in an object key name. However, using certain characters in key names may cause problems with some applications and protocols. The following guidelines help you maximize compliance with DNS, web-safe characters, XML parsers, and other APIs.

Refer to [developer guide](https://docs.aws.amazon.com/AmazonS3/latest/dev/UsingMetadata.html).

## Metadata
There are two kinds of metadata: system metadata and user-defined metadata.

### System-Defined Object Metadata
For each object stored in a bucket, Amazon S3 maintains a set of system metadata.

There are two categories of system metadata:

1. Metadata such as object creation date is system controlled where only Amazon S3 can modify the value.
2. Other system metadata, such as the storage class configured for the object and whether the object has server-side encryption enabled, are examples of system metadata whose values you control.

### User-Defined Object Metadata
When uploading an object, you can also assign metadata to the object. 

## Storage Class
Amazon S3 offers a range of storage classes for the objects that you store. You choose a class depending on your use case scenario and performance access requirements.

See details in [developer guide](https://docs.aws.amazon.com/AmazonS3/latest/dev/storage-class-intro.html)

- **STANDARD** — The default storage class. If you don't specify the storage class when you upload an object, Amazon S3 assigns the STANDARD storage class.

- **REDUCED_REDUNDANCY** — The Reduced Redundancy Storage (RRS) storage class is designed for noncritical, reproducible data that can be stored with less redundancy than the STANDARD storage class.

- **INTELLIGENT_TIERING** - The INTELLIGENT_TIERING storage class is ideal if you want to optimize storage costs automatically for long-lived data when access patterns are unknown or unpredictable.

- **STANDARD_IA** and **ONEZONE_IA** - designed for long-lived and infrequently accessed data. E.g. For storing backups.
