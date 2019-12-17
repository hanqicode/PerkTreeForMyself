# Interaction Testing

## Mocks and Stubs
Tests written with mocks usually follow an `initialize -> set expectations -> exercise -> verify` pattern to testing. 
While the pre-written stub would follow an `initialize -> exercise -> verify`.

See [more info](https://stackoverflow.com/questions/3459287/whats-the-difference-between-a-mock-stub)

## Why need mocks?
Say we have `PersistentUser` and `DAO` two classes.
> What we’re interested in is “Does the PersistentUser method use the DAO correctly?”

```groovy
class MyMockSpec extends Specification {

    @Subject
    Upstream upstream

    Tokenator tokenator = Mock()

    def setup() {
        upstream = new Upstream(tokenator)
    }

    def "can detoken successfully"() {
        given:
            1 * tokenator.detoken("token") >> "plain text"

        expect:
            upstream.detokenInput("token") == "success"
    }
}
```
Notes:  
"assert that exactly 1 call is made to the `tokenator.detoken` method".

