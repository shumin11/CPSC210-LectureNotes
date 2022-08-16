# Construction 1: Throwing and Catching Exceptions

**Robustness: Exceptions and Assertions**
checked exception & unchecked exception 
for unchecked one, it does not need to be listed in the method signature;

if (....) {
    throw new ExceptionName();
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

