# Building Connectors

Conduit connectors can be built in any programming language that supports gRPC. To make it easier to write connectors we provide a [Connector SDK](https://github.com/ConduitIO/conduit-connector-sdk) written in Go. Using the SDK is the recommended way of writing a Conduit connector.

### Conduit connector template

The easiest way to start implementing your own Conduit connector is by using the [Conduit connector template](https://github.com/ConduitIO/conduit-connector-template). It contains the basic project structure as well as some additional utilities like GitHub actions and a Makefile.

Find out more about the template and how to use it in the readme.
