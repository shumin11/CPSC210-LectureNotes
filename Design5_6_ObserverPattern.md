# Design 5: Observer Pattern

Observer setup:
- make classes for abstract subject (not necessarily abstract), and abstract observer (typically abstract or interface)
- put the abstract update() method into the abstract/interface observer
- give the subject a list of Observers, implement addObserver() and notifyObservers().

Consider your situation
- decide who is the observer, and who is the subject/observable - subclass appropriately.
- identify the observable behaviour in the subject (some method that you want the observers to be updated about: let's call this the trigger point.)
- call the notifyObservers method from the trigger point method.
- decide how the observers are going to react to the notification (override the update method in each concrete observer)
- register the observers with the subject, calling addObserver()
- set the whole thing in motion by running the program

**The watcher is referred to as the Observer;**
**The watched object is referred to as the Subject/Observable.**

Registration: the observer registers with the Subject, by calling a registration method on the subject (named something like register, or addObservers). 
In that method, the Subject adds the Observer to its list of Observers.

Notification: When the subject's state changes, it notifies the observers by calling its own notify (or similarly named) method. The notify method then iterates through the list of observers, calling update (or a similarly named method) on each one. The subject may send an argument with this method to indicate the change (the push model), or may send a reference to itself so that the Observer can call back to find out what changed for itself (the pull model).

Subject (addObs(), nofifyObs())  ->(0..*)  Observer(update())

**Observer should be an interface**

**Subject must be a class or abstract class** 
Subject has methods (implementation) (addObserver(Observer observer), notifyObserver(Thing thing));

Observer has method : void update(Thing thing);

# Design 6: Java's Observer

- decide who is the observer, and who is the subject/observable

- identify the observable behavior in the subject (some method, that you want the observers to be updated about)

- Call **setChanged()** and then **notifyObservers()** from the trigger point

- Decide how the observers are going to react to the notification (override the update method in each concrete observer).

- register the Observers with the Subject calling addObserver();

Java's build in support:
The Observer type is an interface that specifies the update method -- meaning any calss that implements the Observer must have this metho present in its implementation.

The Observable type is an abstract class that provides the basic functionality of the role of the Subject. (maintain a list of Observers, has a notifyObservers method that loops throught the list, calling update on each one.) The method seChange() has to be called prior to the call to notifyObservers.


NOTES: Practise question: D4/5/6 Lecture lab (try to do many times!!!)
