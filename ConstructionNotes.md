# Construction 1: Throwing and Catching Exceptions

**Robustness: Exceptions and Assertions**
checked exception & unchecked exception 
for unchecked one, it does not need to be listed in the method signature; no need try/catch neither
"**extends RuntimeException**" not "Exception"

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

# Construction 2: Exception Hierachy/unchecked exceptions/assertions

runtime exceptionsL can be thrown by a method, and do not need to be mentioned in the method signature. 
They also do not force the calling method to "try" to call the method. The calling method can, however, surround the call with try catch if they want to catch a runtime exception

# Construction 3: Testing Exception (example as above)

# Construction 4: Extracting Hierarchy and Associations

Extract a class hierarchy (extends, implements)

Association is all about field!

Below is a summary of one approach you can take to extract a UML class diagram from code:
1. choose a class (X) to represent in the UML Class Diagram;
2. Inspect a class (X) for fields that refer to other classes (Y and Z) in the application;
3. add each class found in step 2 to the UML class diagram;
4. For each field found in step2
- how many objects that field hold?
- is the field initialized with values in the constructor of the class you are insepcing?
- are there methods that can change the cardinality after it is set (if it is) in the constructor?
- visit the class at the end of the association
- consider what the association represents
5. repeat 2-4 for every class you ends up with adding to UML Class Diagram.

# Construction 5: Extracting Sequence Diagrams

Sequence diagrams show interactions between objects
All active objects get their own "lifeline".
Calls are placed in order of when they occur when running the code;
Loops and conditions are placed in enclosing boxes.
Lists can either be shown using a foreach-loop box, or showing access to two list items.

# Construction 6: Implementing a Hierarchy, Simple Fields  

If the type is a collection, determine the kind of collection needed:
- set for unique items and fast searching
- List for maintaining order

Fast for searching (Sets);
Preserves order of insertion (List);
Fast for inserting at the end of the list (Linked List).

# Construction 7: Overriding Equals (and hashcode)

Map<KeyType, ValueType> myMap = new HashMap<>();

List<String> strings = new ArrayList<>();

myMap.values();

myMap.keySet();

myMap.containsKey();

myMap.containsValue();

mayMap.size();

myMap.getKey();

myMap.getValue();

for (Map.Entry<KeyType, ValueType> e : myMap.entrySet()) {
     ValueType value = e.getValue();
     ...
}

myMap.put(myKey, myValue);

ValueType val = myMap.get(myKey);

To find an element in a collection, you must override equals and hashcode for its type.

**Equals and HashSet are normally added in the Key Class**.



# Construction 8: Implementing Bi-Directional Relationships and Sequence Diagram


Bi-directional relationships must be maintained on both sides, and a change in one must be reflected in the other.

A-B (0..*)

public void addB(B b) {
    if (!bees.contains(b)) {
        bees.add(b);
        b.addA(this);
    }
}

public void addA(A a) {
    If (!ayes.contains(a)) {
        ayes.add(a);
        a.addB(this);
    }
}