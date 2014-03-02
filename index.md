---
layout: default

---

jsonbroker
====
**document-version:  0.0.2014.03.02 (pre-alpha)**



A set of libraries for building hybrid applications.


Jsonbroker is centred around a simple JSON structure that structures communication of messages between two modules of code. 

Key Features: 

* Messages are in pure JSON, so are platform independent;
* The message contains all routing information, so messages are transport agnostic;
* supports a request/reply or client/server model.
* has been implemented in Java, Objective-C, and C#. The three main implementations have a single consistent object model;
* is designed with the software development process in mind.


The most typical usage in a *client*/*server* model. It compares closest to JSON-RPC, with a hint of CORBA and DCOM.


###Existing Server Deployment scenarios

* Objective-C embedded in an OSX application;
* Objective-C embedded in an iOS application;
* Java running in the JVM;
* C# running in a Windows .NET desktop application;
* Javascript embedded in a chrome application;
* Javascript embedded in an iOS application.

###Existing Client Deployment scenarios

* Objective-C embedded in an iOS application;
* Java running in the JVM;
* Javascript embedded in a Web Browser;
* Javascript embedded in an OSX application;
* Javascript embedded in an Android app;
* Javascript embedded in an iOS app;


The transport agnostic nature of the messages has significant impact on how applications are developed. The clear separation of client and server means that a allows a flexible approach to development. As an example:

1. During the early stages of development a user interface is implemented in Javascript in HTML in a browser. A set of mock services are provided and hosted on a Java HTTP server. 
2. Afterwards (or in parallel), those same services are implemented in an Android application.
3. As part of integration/system testing, a HTTP server is run on the Android application, the user interface utilises those services over HTTP. 
4. During the final build the HTTP server in Android is disabled or removed, but the Javascript in HTML is embedded within the Android application. The HTTP transport is replaced with an Android specific means of communicating between the Javascript and Java.

The separation between client and server components also simplifies alternate deployment scenarios. Given the example above, the Android services could be re-implemented in Objective-C on iOS and then the HTML/Javascript could be re-used in the client portion of code. 

There is no requirement that Javascript functions only in the role of client. Java code in an Android app could act in the role of a client calling into a service implemented in Javascript in an embedded HTML page.  

