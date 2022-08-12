# Design 7: Basic Iterator
a. To iterate over a privately held data structure within a class, you can make the class implement Iterable. Patameterize it by the kind of element that is inside the data structure.
b.  Then you have to implement the "iterator" method, and return the privately held data structure's own iterator.

public class MyClass implements Iterable<String> {
    private ArrayList<String> mySecreteStringField = new ArrayList<>();  //a

    @Override
    public Iterator<String> iterator() {
        return mySecreteStringField.iterator();
    }

}

This means  we can write loop like 