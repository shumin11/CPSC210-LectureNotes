# Construction 1: Throwing and Catching Exceptions

**Robustness: Exceptions and Assertions**
checked exception & unchecked exception 
for unchecked one, it does not need to be listed in the method signature; no need try/catch neither
"extends RuntimeException" not "Exception"

public void theMethod() throws SomeException {
if (someCondition) {
    throw new SomeException();
}
}

try {
    methodName();
} catch (ExceptionName e) {
    recovery code;
} finally {
    code that will always runs!
}

In Exception class:
public class NotHungry extends Exception{

}

## Assertion
assert placed in the code, rather than in the test class.
eg. assert(!isHungry && (eaten > initialEaten));

Hierarchy for exception:
catch subtypes by catching the supertype exception instead.

@Test
public void testExc {
    try {
        o.theMethod();
        fail ();
    } catch (ExpectedException e) {
        //nothing to do here
    }
}

@Test
public void testExc{
    try {
        o.theMethod();
    } catch (ExpectedException e) {
        fail ();
    }
    assertTrue();
}