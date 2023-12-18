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

## UML

* standardized diagrams that allow you to visualize structural info about code
* up arrow means origin box extends end box
* class name is italicized if class is abstract
