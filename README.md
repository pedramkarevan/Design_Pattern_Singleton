# Design_Pattern_Singleton
Singleton Design Pattern Samples By Java

Singleton Design Pattern
A singleton class has only once instance, accessible globally through a single point (via method or field in singleton class)
It ensures that there is only once instance of your class in your application. Any state you add in singleton class becomes “global state” of your code

UML Diagram:

It is a class that provides static method typically call singleton and this method returns instance of the class and this class is responsible for creating that one instance.

Step by step Implementation:

  1-	Controlling the instance creation
  
    a.	Class constructor must be not accessible globally
    b.	Inheritance must not be allowed
    
  2-	Keeping track of instance
  
  3-	Giving access to singleton instance
  
    a.	A public static method
    
Two option for implementation:
-	Eager singleton

Create singleton as soon as class is loaded

We create a private constructor. Next we will have a private static final field of type of the class which hold initializing our singleton instance at the time of declaration and public static method for providing this field.

-	Lazy singleton

Created when it is first required

We create a private constructor. Next we will have a private static volatile field of type of the class and public static method for providing this field and instantiate the object and assign to final field with synchronization block 


Implementation Consideration

  -	Eager initialization is simplest and preferred way
  
  -	The classic pattern implementation uses double check locking and volatile field
  Design Consideration
  
  -	This pattern does not need any parameters. If you find yourself in need of support for constructor arguments, you need a simple factory or factory method pattern.
  
  -	Make sure that your singleton are not carrying  a lot of mutable global state.

Pitfalls

-	Since they are globally accessible it is easy to miss dependencies.

-	They are hard to unit testing. You cannot mock the instances.

-	Having a mutable global states is bad practice nowadays!

Note:

There are very few situations where a singleton is a good choice :

-	Storing application configuration values. Typically these are read from file at start then refer to by other parts of application

-	Logging framework like log4j

-	Spring framework track all beans by default  as singleton.

