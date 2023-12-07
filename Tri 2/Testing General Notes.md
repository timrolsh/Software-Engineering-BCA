# Testing General Class Notes

* Unit testing is important for the times when you need to maintain code and make sure that complex projects still work
* idea for coding is that you should layer your logic because when the project becomes too complex, it becomes harder and harder to keep track of all layers, logic, and moving parts
* Big production style code bases will eventually become more complex than we can comprehend
* In bad code/spaghetti code, layers are still there but they are not organized in a way that's easily understandable, and you have to try and keep track of everything in your head
* Code graveyard: something nobody can touch because that it will break
* Idea is that you want to avoid code graveyard that you want to be able to change one of many moving parts so that people can isolate layers in development
* 100% test coverage is a bad idea because it now gets to the point that you can't refactor anything cause if you change a little thing all your tests fail
  * sweet spot for test coverage is about 80%
* Testing every possible input guarantees that everything is covered but is expensive and is unnecessary
  * Idea is that most inputs will behave the same way so you don't need to actually test similar stuff over and over again

## Types of Testing

Unit Testing

* do methods and classes do what we expect? We write unit tests that answer this key question
Integration Testing
* Do various small classes and systems interact with each other in the same way we expect?
* These will mostly always be black box tests
System Testing
* done by people after project is released
* Does the entire project work as expected?
Acceptance testing
* done by people after project is released
* Do people/client like the client we've produced?

## Anatomy of Test

* Arrange
  * usually a class will serve as a container for a series of tests
  * Test itself will probably be a function inside the class
  * We want a descriptive function name inside for test functions, as we won't be calling these functions a lot and this acts as your test name, so you want them to be as descriptive as possible
* Act
  * code that goes inside
* Assert: say whether test has passed or failed

## Black Box vs. White Box

* **Black box** is testing on API level, you don't know or assume you don't know whats happening under the hood but you want to make sure you honor api contracts
  * focus on APIs and external behaviors that are being used by other components
  * example: test that makes sure error message appears if user signs in with incorrect username and password and that system checks it
  * *Example*: testing edge cases
* **White Box**: you know all of the details of the implementation and work with that, so you are effectively testing the details of implementation
  * for example testing if there are security vulnerabilities in a login flow: you can sign in but with vulnerabilities, so black box testing alone might not be enough
  * Lots of security conditions are done with white box testing because we acre about internal behaviors there
  * *Example*: Testing that fib function properly makes recursive calls within itself
  * Focus on **code coverage**: how many lines of code of the implementation are you covering?
    * IDEs like Jetbrains help you out with this code coverage
* Grey box: You are testing stuff that you might not necessarily have access to so you do a combination of both black and white box

## Equivalence Class Partitioning

* Ranges: if you're testing password for example, you want to split into parts where its less than the required length, within the required length, and more than the required length
* Enumerables: you only have to test bus one type of enum if you have it, you don't have to test them all
* Domain Charactestistics
