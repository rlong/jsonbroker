---
layout: default
title: Components

---



Components
=================
**document-version:  0.0.2014.03.02 (pre-alpha)**  


Each code implementation is divided roughly into three parts depending on the role the code that a developer is playing.

* *Common*: base framework code.
* *Client*: code that is consuming services (which may be co-located)
* *Server*: code that is providing services


### Common


* **Defaults:** for storing configuration preferences that is an abstraction over some native persistent store.
* **Logging:** a logging library with a focus on context (where, who, what etc.)
* **BaseException:**
* a **[JSON](Components_JSON.html)** parser which offers a DOM style interface and a SAX style event driven interface.
* **WorkManager:** for asynchronous tasks. A thin layer over the native architectures threading model.


### Client


### Server

* **HTTP Server:** a simple threaded HTTP server. It is an implementation with a thread per connection, so is not designed for large scale or internet deployment.


----
