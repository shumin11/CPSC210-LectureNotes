# Design 4 : Composite Pattern

Leaf (operation()) extends Component;
Composite (+ operation(); + add(); +remove(); +getChild()) extends Component;
Composit has 0..* components;

Work steps:
- work out what the composite is (it will be the thing that needs to contain the other thing)
- work out what the "leaf" is
- make sure they both extend component
- give the composite a list of components
- implement the recursive "operation" behaviour in the composite

The **Composite Pattern**, an OO solution for a hierachical structure;

The **Observer Pattern**, a solution for when one/more object(s) wants to watch the state of one /more other onjects;

The **Iterator Paterrn**, which allows us to collect behaviour related to iterating over a collection.

Panel and Component is bi-directional:

in Component:
public void setParent(Panel parent) {
    if (this.parent != parent) {

        if (this.parent != null) {
            this.parent.remove(this);
        }

        this.parent = parent;
        if (parent != null) {
            parent.add(this);
        }  
    }
}

In Panel:

public void add(Component child) {
    if (!children.conatins(child)) {

        Panel parent = child.getParent();
        if (parent != null) {
            parent.remove(child);
        }

        children.add(child);
        child.setParent(this);
    }
}



