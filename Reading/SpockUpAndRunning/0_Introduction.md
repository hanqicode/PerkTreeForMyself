# Introduction

**Spock** is a test framework built on top of **Groovy**.

I would list all advantages here by comparing Spock with JUnit.

## More explicit stack trace
If using JUnit framework, we could have:
```java
public class MyUtilTest {

    private MyUtil util;

    @Before
    public void setUp() {
        util = new MyUtil();
    }

    @Test
    public void testTwoSum() {
        int sum = util.twoSum(1, 2);
        assertEquals(1, sum); // intend to make it fail
    }
}
```

Then its stack trace looks like:
```
java.lang.AssertionError: 
Expected :1
Actual   :3
```

If using Spock framework, we could have:
```groovy
class MyUtilSpec extends Specification {

    def "get sum of two integers"() {
        given:
            def util = new MyUtil()
            def a = 1
            def b = 2

        expect:
            util.twoSum(a, b) == 1 // intend to do so
    }
}
```

Then its stack trace looks like:
```
Condition not satisfied:

util.twoSum(a, b) == 1
|    |      |  |  |
|    3      1  2  false
```
