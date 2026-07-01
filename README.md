# special_methods
1. Constructors in Python (__init__)
• A constructor is a special method in Python called automatically every time a class is  
being used to create a new object.
• It is used to initialize the attributes of an object.
• Without a constructor, every attribute would have to be assigned manually after          
object creation, which is inefficient and error-prone.
Key Points
✓ Named __init__ 
✓ Runs automatically during object creation 
✓ Uses self to refer to the current object 
✓ Ensures objects start in a valid state
Purpose
✓ Assign initial values to object attributes 
✓ Prepare the object for use immediately after creation

2. String Representation Methods
• Pythonprovides two major string representation methods.
✓ Informal Representation: __str__()
✓ Formal Representation: __repr__()
2.1 Informal Representation: __str__()
• The__str__() method provides a human-readable representation of an object.
• Itdefines what should be displayed when an object is printed.
• Without this method, Python displays the object's memory location, which is not
useful to users.
• Thismethod is intended for end users rather than developers

2.2 Formal String Representation ( __repr__() ) 
• The__repr__() method provides an official or developer-oriented representation of an
object.
• Itis primarily used for debugging and logging.
• Ideally, the returned string should contain enough information to recreate the object.
• When__str__() is not defined, Python falls back to __repr__()

3. Length Method: __len__()
• The__len__() method allows custom objects to define what their length means.
• Python's built-in collections such as lists, tuples, dictionaries, and strings all implement
this method.
• By implementing __len__(), custom objects can work naturally with the built-in len()
function.

4. Equality Comparison: __eq__()
• The__eq__() method defines how objects should be compared for equality.
• By default, Python compares whether two variables refer to the same memory
location.
• Manyapplications, however, require comparison based on object content rather than
identity.
• When we call object1 == object2, internally, Python does this
object1.__eq__(object2)

5. Operator Overloading
• Operator overloading allows programmers to define how operators behave when
applied to custom objects.
• Allows operators to work with custom objects.
• Thisenables objects to behave naturally and intuitively.
• Forexample, adding two vectors should produce another vector rather than raising an
error.

6. Item Access: __getitem__()
• The__getitem__() method enables an object to behave like a sequence or container.
• Itallows elements to be accessed using indexing notation, just like lists and tuples.
• Implementing this method makes custom objects more intuitive and compatible with
Python's indexing syntax.

7. Item Assignment: __setitem__()
• The__setitem__() method enables assignment using indexing notation.
✓ It allows assignment using indexing.
• Itallows objects to store or modify values in a way similar to lists and dictionaries.
• Thismethod is commonly used when building custom container classes.

8. Membership Testing: __contains__()
• The__contains__() method defines membership testing for custom objects.
• Itdetermines how the in operator behaves.
• This is useful when an object manages a collection of elements and should support
membership queries

9. Callable Objects: __call__()
• The__call__() method allows an object to be invoked (or behave) like a function.
• This is useful when objects need to maintain internal state while still behaving like
callable functions.
• Manyadvanced Python frameworksuse callable objects extensively

10. Iteration Support: __iter__() and __next__()
• Thesemethods allow objects to work in loops/iteration.
• Together they form the foundation of Python's iterator protocol, which powers for
loops.
• Aniterator must know how to provide the next value and when iteration should stop.

11. Boolean Evaluation: __bool__()
• The__bool__() method determines how an object behaves in Boolean contexts.
• Itbasically controls truth-value testing.
• Itallows objects to define what should be considered True or False.
• Thismethod is commonly used in classes representing states, conditions, or resources.

12. Destructor Method: __del__()
• The__del__() method is known as the destructor.
• Itis called/executed when an object is about to be removed from memory or when an
object is being destroyed.
• Historically it was used for resource cleanup such as closing files or releasing network
connections.
• However, because Python's garbage collection timing is not always predictable,
modern Python programs generally prefer context managers (with statements) for
cleanup tasks.
✓ Avoidrelying on __del__() for critical cleanup operations.
