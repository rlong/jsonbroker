	---
layout: default
title: Scratch Area

---


Scratch Area
------
**document-version:  not-applicable**  



----

-   Is logically made up of 3 basic components

    -   a client, which consumes functionality made available via a

    -   service. Messaging between the client and the server takes place
        via

    -   messages. Messages are composed of JSON strings.

-   JsonBroker is oriented around the concept of Services. These are
    modeled after the facade design patter (ref: Gang-of-4), or COM
    objects in MS-Windows.

-   A Service makes no statement about what type of language it is
    written in. As a corollary, no assertion is made whether it is
    implemented as 0, 1, or many objects.

-   A Service is logical grouping of 1 or more methods.

-   A Service is not required to understand the transport associated
    with the delivery of messages to it;

-   over arching goals

    -   services are transport agnostic;

    -   message structure is lightweight, but flexible enough to
        accommodate future extensions to requirements;

    -   decentralized approach to management of types of services, their
        methods and the errors associated with those methods

    -   some level of authentication of clients in a networked
        deployment is built-in via message digest authentication (ref:
        RFC-2617)

    -   division of responsibilities into at least 2 layers. Core
        business rules \[pragmatic programmer\] implemented in
        services. policy business rules are implemented in clients. In
        addition, aligns somewhat with MVC, 'Model' can be
        implemented as a service. 'View', and 'Controller' implemented
        as a client. Simplifies integration and system testing of a
        service.

-   over arching non-goals:

    -   development utilizing 'cloud' technology.

-   JsonBroker is designed for software developers and organizations
    that

    -   are looking to implement a client/server solution in a
        distributed architecture

    -   understand exceptions, threading, native (objective-c, Java,
        C\#) coding, understand HTML and JavaScript.

    -   want to develop hybrid applications. This includes the
        development of standalone mobile-apps (With built-in services),
        Mobile-apps that utilitise services available on a network.
        Stand alone desktop-applications with bult-in services,
        desktop-applications utilising services available on a network.
        Browser embedded applications that make use of services
        available on a network.

    -   

Scratch
-------

-   Where possible and practical, it is recommended that
    associative-parameters are preferred over ordered-parameters. The
    rationale being that as there is no enforced schema, it is easier to
    detect the absence of required parameters. a JSON object is also
    easier to interpret than an array, as the index into an array
    references a parameter whose purpose is not necessarily clear. A
    name is somewhat better at conveying the intent of a parameter.

-   major-version in a response should always have the same value as
    major-version in the responses associated request.

-   Multiple versions of a service may be made available in order to
    allow backwards compatibility.

Errors and Exceptions
=====================

This is some text

Test

Test 2

Key Classes
===========

Runtime Environment
===================

Development
===========

CSS
===

[target Retina devices in CSS](http://zachwill.com/tumblr-ios/) ... 

    @media only screen and (-webkit-min-device-pixel-ratio: 2) {    /* Retina CSS */
    }

[disable autosizing of text in the CSS](http://stackoverflow.com/questions/1619802/uiwebview-resizes-text-after-rotating-looking-for-explanation-for-magical-bug-o) ...

    html {    
        -webkit-text-size-adjust: none; 
    }

        -webkit-tap-highlight-color:rgba(0,0,0,0);    -webkit-user-select: none;

Glossary
========

-   browser-applications

-   desktop-applications

-   JSON

-   method-name: a JavaScript String identifying a method within a
    service

-   mobile-apps

-   MVC

-   service

Notes/Scratch
=============

* integration testing via `curl`
* poor mans dependency injection
* need to move helper methods from `BrokerMessage` to
`BrokerMessageHelper`.
* need to rename `BrokerMessage.metaInformation` to
`BrokerMessage.metaData`.

Imported from Notes
===================

taken from `notes.jsonbroker/jsonbroker.txt`

-   supports division of responsibilities;
-   does not require any specific IDE/OS for development;
-   integrates (well enough) with Chrome to allow development outside;
-   remote broker;
-   future support for bluetooth;
-   targets browser, desktop, and mobile environments;
-   nothing specific to mobile platforms;
-   sync/async model
-   small js footprint
-   remote broker supports security
-   outside of the JSON objects `<Service>`, implementors do not write
    any specific javascript
   