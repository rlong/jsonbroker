---
layout: default
---

jsonbroker
====
**document-version:  0.0.2014.01.18 (pre-alpha)**  



A set of libraries for building hybrid applications.



Jsonbroker is centred around a simple message structure that allows communication between two pieces of code. The two pieces of code maybe in different languages, different runtimes, different processes, or different machines. 

The most typical use is between a *client* (caller) invoking methods on a *server* (callee). This involves one *request* message being passed to from the client to the server and then the server passing back a *response* to the client. The request  structure contains all required routing information so the message is transport agnostic. Request messages are unmarshalled by the jsonbroker library and passed to a developer provided module known *service* which processes the request and passes back a response object which the jsonbroker library attempts to return the response to the client.

One of the key features of the jsonbroker library is that messages are transport agnostic. This has significant impact on how applications are developed. The separation of client and server means that a allows a flexible approach to development. As an example:

1. During the early stages of development a user interface is implemented in Javascript in HTML in a browser. A set of mock services are provided and hosted on a Java HTTP server. 
2. Afterwards (or in parallel), those same services are implemented in an Android application.
3. As part of integration/system testing, a HTTP server is run on the Android application, the user interface utilises those services over HTTP. 
4. During the final build the HTTP server in Android is disabled or removed, but the Javascript in HTML is embedded within the Android application. 

The separation between client and server components also simplifies alternate deployment strategies. Given the last example, it is easy to imagine reimplementing the Android services in Objective-C on iOS and then re-using the client portion of the code. 

It is worth noting that there is no requirement that Javascript functions only in the client role. It is possible to consider Java code in an Android app being the making calls to a service implemented in Javascript in an embedded HTML page.  


The jsonbroker library was built initially for mobile applications with embedded HTML pages, but has been since extended. Some examples that have been implemented include: 

|Client|Intermediary|Server|
|------|------------|------|
|Objective-C in an iOS App|UIWebView|Javascript in HTML in an iOS App|
|Javascript in HTML in an iOS App|UIWebView|Objective-C on an iOS App|
|Javascript in HTML in an iOS App|android.webkit.WebView|Java on an Android App|
|Javascript in HTML in an OSX Application|WebView|Objective-C in an OSX Application|
|Javascript in HTML in a Windows application|System.Windows.Forms.WebBrowser|C# in a Windows application|
|Javascript in HTML in a Browser|HTTP|Objective-C in a HTTP server on iOS|
|Javascript in HTML in a Browser|HTTP|Java in a HTTP server|
|Objective-C in an OSX application|NSAppleScript|Applescript in an OSX application|
|Java in a Android app|Bluetooth (RFCOMM)|Objective-C in an OSX application|
|Javascript in a Chrome app|HTTP|Java in a Android app|
|Java in a Android app|TCP/IP|Javascript in a Chrome app|

Most of the above have been deployed to end-users.