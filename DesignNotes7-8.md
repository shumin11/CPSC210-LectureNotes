# Design 7: Basic Iterator
a. To iterate over a privately held data structure within a class, you can make the class implement Iterable. Patameterize it by the kind of element that is inside the data structure.
b.  Then you have to implement the "iterator" method, and return the privately held data structure's own iterator.

public class MyClass implements Iterable<String> {
    private ArrayList<String> mySecreteStringField = new ArrayList<>();  

    @Override
    public Iterator<String> iterator() {
        return mySecreteStringField.iterator();
    }

}

This means  we can write loop using the class directly

MyClass myObj = new MyClass();
for (String s : myObj){
    system.out.println(s);
}

In Java, there are three kinds of abstraction
- procedural abstraction
- data abstraction
- iteration abstraction

... class ArrayList<E> implements List<E> {
    public Iterator<E> iterator() {
        return new ArrayListIterator<E>();
    }
}
Collection is an interace that extends Iterable:
public interface Collection<E> extend Iterable<E> ...

Iterator Class: each collection has its own version of iterator;
a. cursor (track where you are)
b. bool hasNext(), true is there is more element in the collection
c. Element getNext(), has all the logic to figure out where next one is and return the next element to the caller

ArrayList implements Collection extends Iterable;
ArrayListIterator method will show in the ArrayList.
Inside the ArrayListIterator method, we see the methods of hasNext() and getNext();

for (Toy t: inventory) {}
Iterator<Toy> ti = inventory.iterator();
while(ti.hasNext()) {
    Toy t = ti.getNext();
}

Every kind of collection needs its own iterator, because each collection has its own structure;
Each of those iterators **extend** the Iterator Interface (specifying the **next** and **hasNext** methods), and the collections each implement the Iterable Interface.

**LinkedHashSet:**
Maintains the order, does not allow duplicate channels;

In String Class that Java build in, it has
public boolean startsWith(String prefix) method;

**ConcurrentModificationException**:
 is used to fail-fast when something we are iterating on is modified.
 **Solutions**:
 1. using an Iterator directly
 because iterator.remove() does not cause a ConcurrentModificatonException.
 
 public void removeThingThatStartWith(String prefix) {
  for (Iterator<Thing> iterator = things.iterator(); iterator.hasNext();) {
    Thing thing = iterator.next();
    if (thing.getName().startsWith(prefix)) {
        iterator.remove();
    }
  }

  2. Not removing during Iteration
add a list, and use removeAll() method;

public void removeThingThatStartWith(String prefix) {
    List<Thing> toRemove = new ArrayList<>();
    for (Thing thing: things) {
        if (thing.getName().startsWith(prefix)) {
            toRemove.add(thing);
        }
    }
    things.removeAll(toRemove);
}

3. Methods provided by Instructor

Iterator<Thing> thingIterator = things.iterator();
while (thingIterator.hasNext()) {
    Thing nextThing = thingIterator.next();
    if (nextThing.getName().startsWith(prefix)) {
        thingIterator.remove();
    }
}


# Design 8: Advanced Iterator

Class implement Iterable<ElementType>, return an instance of Iterator I make!

Home-made iterator for your collection must be a private **inner class**. 
(because the Iterator code needs access to the private data field inside your class)

Inner Iterator needs:
a. to implement Iterator<ElementType>

b. a counter of some kind to keep track of where it is

c. a hasNext() that returns true if there are more elements, false otherwise

d. a next() method that returns the next ElementType, and moves the counter along

private class CustomIterator<TheElement> implements Iterator<TheElement> {
    private Placeholder cursor;

    public boolean hasNext() {
        // check if the collection has any elements left to iterate over
        // based on the location of the cursor
    }

    public TheElement next() {
        // increments the cursor appropriately
        // return the element at the cursor
    }
    
}

Below is for 
return taByTeam.values().iterator();









  