---
layout: default
title: Services

---



Services
=================
**document-version:  0.0.2014.03.02 (pre-alpha)**  



### Semantic Versioning

(**TODO**: Semantic Versioning: F7BA076F-10CA-4492-82C4-52D6B7839A57)

### Naming Conventions

It is recommended service names follow these conventions:

* A service is named with at least 2 components separated by a period character ('.')
* The first component relates to the module that that the service is implemented in.
* The second component relates to where or what functionality is availble in that service. In the interests of convenience, it is recommend name is close to the class that provides the implementation of the service.

As an example there is a packaged service that comes with all implementations of jsonbroker called `jsonbroker.TestService`. The first name component relates to the name of the module `jsonbroker`, the second name component refers to the class `TestService` ( [TestService.java](https://github.com/rlong/jsonbroker.java/blob/master/src/jsonbroker/library/service/test/TestService.java), [TestService.cs](https://github.com/rlong/jsonbroker.c_sharp/blob/master/service/test/TestService.cs), [JBTestService.m](https://github.com/rlong/jsonbroker.objective_c/blob/master/src/jsonbroker.library/service/test/JBTestService.m)).


----
