# Specification Basics

## First Specification
```groovy
import spock.lang.*

class IntegerSpec extends Specification {
    def "an integer can be incremented"() { 
        given:
            int i=1 
        
        when:
            i++ 
        
        then:
            i==2 
    }
}
```

By convention, the specification class name ends with "Spec" but can be anything at all.

## Block Symantics
Commonly known as "arrange, act, assert or given, when, then". Essentially:

- Given... some preconditions are in effect  
- When... an action is taken
- Then... the outcome is x

This pattern follows suggestion in clean code that "Build, Operate, Check".

Below are complete block semantics:
- `given`:  
Used for establishing the context of the test. Things like creating objects, setting up specific data.
- `when`:  
Contains the behavior being tested.
- `then`:  
Makes assertions about the outcome of the `when:` block.  
A `then:` block must be preceded by a `when:` block.
- `expect`:  
Makes assertions in the same way as a `then:` block but without requiring a preceding `when:` block.
- `cleanup`:  
Allows the safe tear-down of resources. You can think of this as analogous to the `finally` keyword.
- `where`:  
This is used for parameterized feature methods.
- `and`:  
This is used to extend any preceding block. 
This is useful purely to break up the blocks to make them easier to read.

See an example:
```groovy
def "a user can follow another user"() {
    given:
        def user = new User("Jack") 
        def other = new User("Bob")
    expect:
        user.following.isEmpty()
    when:
        user.follow(other)
    then:
        user.following.size() == 1
        user.following.contains(other)
}
```

