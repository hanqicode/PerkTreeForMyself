# General
Homepage: https://projectlombok.org/

## Motivation
It will make our code cleaner by using Lombok.
I will focus on Lombok **Stable** features here.

## Features

### @NonNull
[Detailed link](https://projectlombok.org/features/NonNull)

Add `@NonNull` on the parameters of:
1. a method
2. a constructor

to have lombok generate a null-check statement for us.

It will throw `NullPointerException` if it is null.

```java
public void doSomething(@NonNull final String name) {
	// omitted here
}
```
