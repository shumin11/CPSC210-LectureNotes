# Basics1-5 : Program Structure


Data flow:
- variables get a location in memory to store their value;
- we can assign values to variables - storing their value in that spot in memory;
- y = x, copies the value from x's memory spot to y's memory spot, regardless of whether this is a primitive value or an object reference;
- Object a = b; copies the reference held in b into a's memory's slot. Now they refer point to the same object. 

primitives (like int and boolean), are passed int methods by copying their values, so when the method returns, the original variation doesn't change.

objects(like Dog and ArrayList<Integer>) are passed into methods as copies of references.

Call Graph & FlowChart


start -> if i=3 -->( True -> print yup -> print yay -> print done) -> False -> print done -> end

For Loop: start -> more elements in collection -> get next -> code block-> (go back to more elements in collection)   more elements in collection -> end