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
@RunWith(EasyMockRunner.class)
public class EasyMockExample extends EasyMockSupport {

    private ClassTested target;

    @Mock(MockType.STRICT)
    private Collaborator collaborator;

    @Before
    public void setUp() {
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
2. Use annotations to make it concise: Add `@Mock` and `@RunWith(EasyMockRunner.class)` instead of using `createMock`.
3. Use `MockType.STRICT` to check the order of method calls.
4. Use `Build-Operate-Check Pattern` for test.

## Reference
1. EasyMock Homepage: http://easymock.org/
2. Clean Code.

