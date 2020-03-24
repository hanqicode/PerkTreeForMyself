# General
Homepage: http://easymock.org/

## Motivation
When writing unit tests in Java, there are some dependencies in target class that: 
1. we don't care about detailed implementation.
2. it's unnecessary to get an actual response in unit tests.

So we will mock these dependencies with EasyMock.

## Example
There are many ways to write unit tests with EasyMock, and here is just my preference.

This is the class that need to be tested:
```java
@AllArgsConstructor
public class ClassTested {

    private final Collaborator listener;

    public boolean addDocument(String title) {
        return listener.documentAdded(title);
    }

    public int getDocumentCount() {
        return listener.getDocumentCount();
    }
}
```

This is the interface that need to be mocked:
```java
public interface Collaborator {

    boolean documentAdded(String title);

    int getDocumentCount();
}
```

This is the unit test:
```java
public class EasyMockExample extends EasyMockSupport {

    private ClassTested target;

    private Collaborator collaborator;

    @Before
    public void setUp() {
        collaborator = createStrictMock(Collaborator.class);
        target = new ClassTested(collaborator);
    }

    @After
    public void tearDown() {
        resetAll();
    }

    @Test
    public void testWithEasyMock() {
        // build
        expect(collaborator.documentAdded("Title")).andReturn(true).times(1);
        expect(collaborator.getDocumentCount()).andReturn(1).times(1);
        replayAll();

        // operate
        boolean actualStatus = target.addDocument("Title");
        int actualCount = target.getDocumentCount();

        // check
        verifyAll();
        assertTrue(actualStatus);
        assertEquals(1, actualCount);
    }
}
```

Some comments:
1. Extending or creating an object `EasyMockSupport` is useful but not mandatory. It allows to call `replayAll`, `resetAll` and `verifyAll`.
2. Use `createStrictMock` to check call order.
3. Use `Build-Operate-Check Pattern` for test.
4. `@RunWith(EasyMockRunner.class)`: JUnit runner used to process `@Mock` and `@TestSubject` annotations. 

    4.1  Note that this pattern needs to be used for no parameters constructor to do field injection, see [GitHub Issue Request](https://github.com/easymock/easymock/issues/185).
    
    4.2  Note that this runner only works with JUnit 4.5 or higher.

## Reference
1. EasyMock Homepage: http://easymock.org/
2. Clean Code.

