---
layout: default
---



Message Structure
=================

In it's most basic form, a pair of JsonBroker handles the passing of a
the passing of a request fom a caller to a service and then the passing
of a response from the service to a the same called. A JsonBroker
Message is simply a JSON array. A simple request sent to a service would
look like

    ["request",{},"jsonbroker.TestService",1,0,"ping",{}]

1.  `"request"` is a string that represents the type of message;

2.  `{}` is an empty JSON object that serves as a placeholder for
    metadata that might accompany a request;

3.  `"jsonbroker.TestService"` is a string that identifies the service
    that the request is to be directed to.

4.  `1` is a number that represents the major version of the service
    that is required for the correct processing of a request.

5.  `0` is a number that represents the minimum minor version required
    for the correct processing of a request.

6.  `"ping"` is a string that identifies a method/function within a
    service.

7.  `{}` is an empty JSON object that serves as a placeholder for named
    (associative) parameters to be passed to the method/function
    previously identified.

The corresponding response from a service would look like

    ["response",{},"jsonbroker.TestService",1,0,"ping",{}]

A ordered breakdown of the fields of the array:

1.  `"response"` is a string the represents the type of message;

2.  `{}` is an empty JSON object that services as a placeholder for
    metadata that might accompany a response;

3.  `"jsonbroker.TestService"` is string that identifies the service
    that created the response;

4.  `1` is a number that represents the major version of the service
    that created the response.

5.  `0` is a number that represents the minor version of the service
    that created the response.

6.  `"ping"` is a string that identifies the method within the service
    that was called;

7.  `{}` is an empty JSON object that serves as a placeholder for named
    (associative) parameters that might be passed back from a method.

More formally, a JsonBroker message is a JSON array with at least 7
entries. An eighth optional parameter can also be included if the
receiver of the message is expecting :

1.  message-type; this is a string specifying the category of the
    message.

2.  meta-information; this is a JSON object;

3.  service-name; this is a string specifying the service associated
    with the message

4.  service-major-version number; the is an integer specifying the major
    version of the service, it's exact semantics depend on the
    message-type;

5.  service-minor-version number; this is an integer specifying the
    minor version of the service; it's exact semantics depend on the
    message-type;

6.  method-name; this is a string that identifies a method that is
    associated with a service.

7.  associative parameters; this is a JSON object containing contextual
    information associated with the method identified by method-name
    that is bound to a service identified by service-name;

8.  ordered parameters; this is an optional JSON array. It is a list of
    ordered parameters associated with the method-name

----
