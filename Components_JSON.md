---
layout: default
title: Services

---



JSON Support
=================
**document-version:  0.0.2014.03.02 (pre-alpha)**  


The JSON support was implemented to provide:

* a consistent API across languages;
* strongly enforce behaviour in relation to null values;
* strongly enforce behaviour in relation to default values.

Other properties include:

* objects that represent JSON objects and arrays are mutable and not thread safe.
* API does not provide coercion outside of numeric types (a JSON boolean is not considered a numeric type).

### Key Packages

#### jsonbroker.library.common.json

* Java: [jsonbroker.library.common.json](https://github.com/rlong/jsonbroker.java/tree/master/src/jsonbroker/library/common/json)
* C#: [jsonbroker.library.common.json](https://github.com/rlong/jsonbroker.c_sharp/tree/master/common/json)
* Objective-C: [jsonbroker.library/common/json](https://github.com/rlong/jsonbroker.objective_c/tree/master/src/jsonbroker.library/common/json)


### Key Classes 

#### JsonArray

The `JsonArray` represents a JSON array. In terms of implementation, it is a thin wrapper around a languages Array type. Sparse arrays are not supported. 

* Java: [JsonArray.java](https://github.com/rlong/jsonbroker.java/blob/master/src/jsonbroker/library/common/json/JsonArray.java)
* C# [JsonArray.cs](https://github.com/rlong/jsonbroker.c_sharp/blob/master/common/json/JsonArray.cs)
* Objective-C: [JBJsonArray.h](https://github.com/rlong/jsonbroker.objective_c/blob/master/src/jsonbroker.library/common/json/JBJsonArray.h)


#### JsonArrayHelper

A class with a static set of methods that encapsulates reading a `JsonArray` object from a variety of sources. The class also has a set of methods that encapsulates conversion of a `JsonArray` object to other data types (e.g. array of bytes).

* Java: [JsonArrayHelper.java](https://github.com/rlong/jsonbroker.java/blob/master/src/jsonbroker/library/common/json/JsonArrayHelper.java)
* C# [JsonArrayHelper.cs](https://github.com/rlong/jsonbroker.c_sharp/blob/master/common/json/JsonArrayHelper.cs)
* Objective-C: [JBJsonArrayHelper.h](https://github.com/rlong/jsonbroker.objective_c/blob/master/src/jsonbroker.library/common/json/JBJsonArrayHelper.h)

#### JsonDocumentHandler

A SAX (Simple API for XML) style interface for processing JSON documents. Instead of implementing all the methods specified in this interface. A developer may choose to extend the class `DefaultJsonHandler` ([DefaultJsonHandler.java](https://github.com/rlong/jsonbroker.java/blob/master/src/jsonbroker/library/common/json/DefaultJsonHandler.java), [DefaultJsonHandler.cs](https://github.com/rlong/jsonbroker.c_sharp/blob/master/common/json/DefaultJsonHandler.cs), [JBDefaultJsonHandler.h](https://github.com/rlong/jsonbroker.objective_c/blob/master/src/jsonbroker.library/common/json/JBDefaultJsonHandler.h)) which provides an empty implementation of all the methods defined in `DefaultJsonHandler`. (**TODO**: how to use this class (7D5A7995-1C63-49ED-AB86-83678C7834F5))


* Java: [JsonDocumentHandler.java](https://github.com/rlong/jsonbroker.java/blob/master/src/jsonbroker/library/common/json/JsonDocumentHandler.java)
* C# [JsonDocumentHandler.cs](https://github.com/rlong/jsonbroker.c_sharp/blob/master/common/json/JsonDocumentHandler.cs)
* Objective-C: [JBJsonDocumentHandler.h](https://github.com/rlong/jsonbroker.objective_c/blob/master/src/jsonbroker.library/common/json/JBJsonDocumentHandler.h)


#### JsonObject

The `JsonObject` represents a JSON array. In terms of implementation, it is a thin wrapper around a languages Dictionary or HashMap types. 

* Java: [JsonObject.java](https://github.com/rlong/jsonbroker.java/blob/master/src/jsonbroker/library/common/json/JsonObject.java)
* C# [JsonObject.cs](https://github.com/rlong/jsonbroker.c_sharp/blob/master/common/json/JsonObject.cs)
* Objective-C: [JBJsonObject.h](https://github.com/rlong/jsonbroker.objective_c/blob/master/src/jsonbroker.library/common/json/JBJsonObject.h)

#### JsonObjectHelper

A class with a static set of methods that encapsulates reading a `JsonObject` object from a variety of sources. The class also has a set of methods that encapsulates conversion of a `JsonObject` object to other data types (e.g. array of bytes).

* Java: [JsonObjectHelper.java](https://github.com/rlong/jsonbroker.java/blob/master/src/jsonbroker/library/common/json/JsonObjectHelper.java)
* C# [JsonObjectHelper.cs](https://github.com/rlong/jsonbroker.c_sharp/blob/master/common/json/JsonObjectHelper.cs)
* Objective-C: [JBJsonObjectHelper.h](https://github.com/rlong/jsonbroker.objective_c/blob/master/src/jsonbroker.library/common/json/JBJsonObjectHelper.h)


----
