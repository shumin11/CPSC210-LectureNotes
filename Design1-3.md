# Design 1: Cohesion and Coupling

Cohesion (the single responsibility principle)
check which methods use which fields, and draw an informal usage graph. If there are distinct clusters in the picture, then it is likely be safe to split into two classes.

Coupling:
a. Moderate Coupling: is the coupling that can be found at the compiling time;
b. Semantic Coupling: classes  depending on the implementation of another class.
You want to make change only in one place. If you have make edits in multiple places to make a single change, then you have **bad** coupling.

Single Responsibility Principle: each class should be centered around one cohesive concept;


Coupling between two classes indicates that two classes collaborate in some way.
Inter-class coupling can be through calls, dependencies, or by holding functionality in common that accomplishes a goal without explicitly declaring as such. 

If your design became less cohesive over time, it would:
- be harder for a developer to reason about a class in isolation of others
- be harder for a developer to locate code related to some funcionality in the system
- be harder to reuse some piece of functionality outside the system in which it was developed
- increase the likelihood we will break one concept when implementing a change for another concept


# Design 2: Liskov Substitution Principle (HAPPY FACE)

Subtype can not break the expections set by their supertypes.
NOT substitutable if :
- it narrows the range of acceptable inputs
- it widens the range of possible outcomes

every method in the subtype must be happy. (wider/looser/weaker precondition; narrower/tighter/stronger postconditions)

MAP "preconditions" to REQUIRES clause
how to fix the non-substituable situation: a. change relationship to association or dependency; b. create an interface to abstract away the specific method, then another subtype would have no expection to that method.

**If the class can't perform all the behaviour of superclass, it is weakening the postcondition of those methods, so it violates the Liskov Substituion principle.** 

# Design 3: Refactoring

Purpose: improve cohesion and coupling

Improving Coupling by Abstracting Duplicated Code into Methods
- identify code clones, and pull them into methods;
- make sure to pass in the right parameters, and get the return values correct;

Improving the SRP(single responsibility principle) by **splitting up a class**
- move fields and methods into the new class;
- probably make the new class a field of the old class;

Reasons for Refactoring our code:
1. to decrease duplicate code
2. to increase cohesion
3. to improve readability



