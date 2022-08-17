# Abstraction 1: Specifying and Using a Data Abstraction

Visibility: public,private, protected

Specifying a Data Abstraction: REQUIRES, MODIFIES, EFFECTS

# Abstraction 2-3: Testing a Data Abstraction

create tests that each branch of your method is followed;
write test cases to test the edges of ranges (boundary checking);
Test case should be named after the method they are testing;
test cases always specify the inputs, and the expected outcome;

@Test
- set up
- call the method to test
- check that the expected outcomes occurred

assertTrue, assertFalse, assertEquals

Testing:
 1. bounday cases (endpoints of an interval)
 2. typical case (midpoint of an interval)
 3. test all aspects of the EFFECTS clauses (true/false)
 4. test that the bahaviour of the method is as expected when called multiple times especially when the method has a MODIFIES clause

 Steps:
 1. write set up code
 @BeforeEach @Test
 2. write comments to 3 parts of the test
 - check the setup is correct
 - call the method to test
 - check the outcomes were expected

 ArrayList (add(), remove(), get(index), contains(), size())

 # Abstraction 4-7: Types and Interfaces

 Classes, Interfaces, Abstract classes

 Classes can implement multiple interfaces, but can only extend one abstract class

only protected and public fields and methods are inherited -- private ones are not!

The super keyword is used to refer to a class's superclass.
super() calls the constructor;
super.someMethod() calls the superclass's implementation of someMethod.
