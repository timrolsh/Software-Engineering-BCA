# Design Patterns

* add abstraction to codebase, but abstraction can lead to you overdoing stuff and making it more complicated than it needs to be
* allow you to let compiler enforce any kind of rules you want for any program action in your code and make it easier to change the behavior of your code
  * don't add more design patterns unless necessary, will help avoid unnecessary complexity

## Fasad Pattern

* a shallow class that sits in front of the class you need, acts as an interface to avoid direct calls to a library that has the potential to change or be deprecated
  * shallow class means that it does not do any work
* everything points at the fasad, and you can do all of your work at the fasad

## Singleton

* design pattern that enforces that there is only one instance of a class

## State Pattern

## Observer Pattern

* It's generally bad practice to have block of code that's constantly accessing many other parts of the program
* Way for one object to ask another object for information
* Makes an object 1 (subject) push information to object 2 (observer) as opposed to object 2 constantly asking object 1 for information (pulling)
* The subject is the thing that is being observed, the observer is the thing that is observing the subject
  * The subject calls the callback function of the observer
    * The subject subscribes and unsubscribes to the observer

### Standard Observer Pattern

* One object has a callback function for another object, that other object calls the callback function to let the first object know that something has happened

## Service Locator, Dependency Injection

* `Is a` relationship is inheritance (class B extends class A)
* `Has a` relationship is composition (class A has a class B)
* **Dependency**: When one class A has another class B (composition), class A depends on class B for its proper functionality, so class B is a dependency of class A
  * Disadvantages: No reusability, chain of access from one object to another dependency
* **Service Locator**: Has a class that contains a bunch of other classes that will be dependency for the app, all dependencies are shared instead of just being under one class, easier to implement and access but harder to control and organize
* Dependency by composition and dependency injection are basically the same, just composition has creation of dependencies internally while dependency injection uses external injection

## Decorator

* Object that goes in and modifies the properties of another object, decorates the other object in a sense
* downsides are that is adds complexity and doesn't remove any attributes, just adds new attributes

## Factory Pattern

* A class that many other subclass extend, that main class, the factory, creates its subclasses, easier to manage and create stuff
  * You can also have a separate factory class, and then an interface that all the other classes created by the factory implement
* Downsides are that it adds complexity and create many subclasses
* You can chain factory creations, one factory creates an interface and then multiple classes can extend that interface

## Command Pattern

* Command Class: stores a client object, executes the actual command
* Client Class: requests and creates commands to be executed, passes those commands into the invoker class
* Invoker Class: Stores all of the command objects, determines when to run the commands and sends them off to receiver class
* Receiver Class: rReceiver commands from from invoker and executes them
* This pattern is good for requests, queueing up requests, undoing actions, allows you to de-couple code, the action itself (command) from the block that actually knows how to execute the command (receiver)

## UML

* standardized diagrams that allow you to visualize structural info about code
* up arrow means origin box extends end box
* class name is italicized if class is abstract
