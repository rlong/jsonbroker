---
layout: default
title: A Short Primer on Objective-C

---

A Short Primer on Objective-C
====
**document-version:  0.0.2014.03.02 (pre-alpha)**

This document is intended for developers who are already familiar with another programming language and understand the differences between the memory models of C vs. Java/C#.

It does not cover a number of aspects (e.g. threads, unit-testing) but should start as a starting primer for those who would like to become familiar with Objective-C and developing programs for OSX or iOS.


### Regarding the Language

* read the [Objective-C Wikipedia page](http://en.wikipedia.org/wiki/Objective-C)
* read [Programming with Objective-C](https://developer.apple.com/library/mac/documentation/cocoa/conceptual/ProgrammingWithObjectiveC/Introduction/Introduction.html) ([pdf](https://developer.apple.com/library/mac/documentation/cocoa/conceptual/ProgrammingWithObjectiveC/ProgrammingWithObjectiveC.pdf))available from Apple.
* Objective-C `properties` are object member variables exposed through generated accessors.
* Objective-C `protocols` are equivalent to interfaces in Java and C#
* The convention is to declare a class in a `.h` file and put the implementation in a `.m` file. There are no restrictions on how many classes and can be declared in a single `.h` file and implemented in a single `.m` file. 
* Objective-C method calls are not statically bound in the same sense as C, Java, C#. Objective-C objects are much more loosely coupled. It is better to think in terms of objects sending each other messages (similar to Javascript or Smalltalk). This is facilitated at runtime by a low level VM.
* Each object has a reference count (set to 1 on allocation) and the objects memory is reclaimed when the reference count reaches 0. 
* Composite objects take ownership of other objects explicitly by sending a `retain` message to an object, this increments the reference count. Calling `retain` on an object is a declaration that the caller is taking (possibly shared) ownership of an object.
* Composite objects release ownership of other objects explicitly by sending a `release` to an object, this decrements the reference count. Calling `release` on an object is a declaration that the caller is releasing ownership of an object. 
* Building an object is a two stage process:
	* object memory is allocated via a call to 'alloc' on the class (e.g. `[NSString alloc]`).
	* constructors are used to initialise the internal state of the object. They are called 'init' or 'init$$$' where $$$ is some name, for example:
	
		NSString* x  = \[\[NSString alloc\] initWithUTF8String:"c string"\];

* There is support for class methods, this is indicated by a '+' at the start of the method signature.
* Instance methods are indicated by a '-' at the start of the method signature.
* There are two main forms of memory model:
	* the traditional model where the developer explicits calls `retain`/`release` methods on an object. The developer must ensure `retain` and `release` messages are balanced. If more calls are made to `retain` than `release`, the object will never have it's memory released and will never get the chance to clean up other resources (e.g. close open files). If more calls are made to the  `release` than the `retain`, then the object will be removed from memory even if there is other parts of the code that still has pointers to the objects memory address.
	* using automatic reference counting (ARC) where the compiler automatically generates `retain`/`release` calls.
 * There is a weak equivalent to Java Listeners. The convention is to name listener style objects as as  a `delegate`. objects that have delegates do not `retain` their delegate and hence make no statement about ownership of the delegate. This avoids [reference cycles](http://en.wikipedia.org/wiki/Reference_counting#Dealing_with_reference_cycles).


###Regarding APIs

* All classes typically extend `NSObject`, this is where you get support for things like reference counting. The `NS` stands for NextStep.
* There are basic collection types defined: `NSArray`, `NSDictionary` etc. These are immutable but have mutable sub-types (e.g. `NSMutableArray`, `NSMutableDictionary`)
* There are basic data types defined: `NSString`, `NSNumber`, `NSDate`. Some are immutable but have mutable sub-types ()e.g. `NSMutableString`).
* GUI work centres on the Model-View-Controller (MVC) pattern.
	* The View is defined in NIB/XIB files, and manipulated part of XCode called 'Interface Builder'.
	* The same NIB/XIB files define the Controller that is associated with the View. The Controller is typically an Objective-C class built by the developer.
	* Methods defined in the Controller can be connected to graphical elements (e.g. Buttons) using 'Interface Builder'.
* A more decoupled notification system that functions as an alternative to the `delegate` idiom above is available via the API. See the [NSNotification](https://developer.apple.com/library/mac/documentation/cocoa/reference/foundation/classes/NSNotification_Class/Reference/Reference.html) class for more information.


### Regarding Development

* The [iOS Programming Guide](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/Introduction/Introduction.html) ([pdf](https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/iPhoneAppProgrammingGuide.pdf)) is a good starting point before beginning any iOS work.
* It is not possible to deploy apps on to a device without developer program subscription ($100 a year as of 2014).
* Early on when beginning development, allow memory to leak. Focus on the job at hand and address memory management as a distinct activity after the code functions as expected. some refactoring may result, but this is better than trying to factor in multiple concerns during development.


### Regarding the Runtime

* All Apple Applications (OSX/iPhone) use the main thread to service requests from the GUI (e.g. button press). These requests are serviced in a non terminating event loop. See [NSRunLoop](https://developer.apple.com/library/mac/documentation/cocoa/reference/foundation/classes/NSRunLoop_Class/Reference/Reference.html) for more information. 
* There is a property list (a set of name-value pairs) associated with each Application. This file indicates the initial View and Controller via a reference to a NIB/XIB file.
	
----
