# Connectors

A connector knows how to read/write records from/to a data source/destination (e.g. a database).

When thinking about connectors for Conduit, our goals were to:

* provide a good development experience to connector developers,
* ship Conduit with real built-in connectors (compiled into the Conduit binary),
* to make it as easy as possible to write plugins in _any_ programming language,
* the [Connector SDK](https://github.com/conduitio/conduit-connector-sdk) to be decoupled from Conduit and be able to change without changing Conduit itself.

Have a look at our connector docs to find out more!
