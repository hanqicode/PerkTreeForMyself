# Adapter



## What is Adapter?
Now I have a macbook with interface Thunderbolt2. I have a monitor and its interface(cable) is Thunderbolt2. 
I can extend successfully.

Now I want to extend/change another monitor but its interface(cable) is HDMI. 
We cannot plugin HDMI cable to macbook's Thunderbolt2 interface directly.

Then we need an adapter to 
1. accept input HDMI
2. output an interface to Thunderbolt2.

Picture like below:

<img src="https://github.com/hanqicode/PerkTreeForMyself/blob/master/Java/DesignPattern/Pictures/Adapter.png" alt="drawing" width="400"/>

## Example
Say we have a Weblab interface and Weblab implementation currently. Like below:

```java
package adapter;

public interface Weblab {

    String getTreatment(String id);
}
```

```java
package adapter;

public class WeblabImpl implements Weblab {

    private WeblabClient client;

    public WeblabImpl() {
        client = new WeblabClient();
    }

    public String getTreatment(String id) {
        return client.getTreatmentBasedOnId(id);
    }
}
```

We don't describe `WeblabClient` details here, because we it is Weblab service client and we do not need to know its implementation here.

Also, we have a class that uses `Weblab` interface to do business logic. Like below:

```java
public class Test {

    public static void main(String[] args) {
        Weblab weblab = new WeblabImpl();

        System.out.println(weblab.getTreatment("ABC")); // C
        System.out.println(weblab.getTreatment("123")); // T1
    }
}
```

Now, we have a requirement to use `RandomClient` to replace `WeblabClient`, but we do not want to change the `Weblab` interface. Here we need to create an adapter. Like below:

```java
package adapter;

public class RandomToWeblabAdapter implements Weblab {

    private RandomClient client;

    public RandomToWeblabAdapter(RandomClient client) {
        this.client = client;
    }

    public String getTreatment(String id) {
        if (1 == client.getRandomNumberBasedOnInput(id)) {
            return "C";
        } else {
            return "T1";
        }
    }
}
```

Then the main class would be:

```java
public class Test {

    public static void main(String[] args) {
        Weblab weblab = new RandomToWeblabAdapter(new RandomClient());

        System.out.println(weblab.getTreatment("ABC")); // C
        System.out.println(weblab.getTreatment("123")); // T1
    }
}
```
