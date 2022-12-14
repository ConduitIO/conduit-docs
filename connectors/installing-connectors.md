# Installing Connectors

Conduit ships with a number of built-in connectors:

* [File connector](https://github.com/ConduitIO/conduit-connector-file) provides a source/destination to read/write a local file (useful for quickly trying out Conduit without additional setup).
* [Kafka connector](https://github.com/ConduitIO/conduit-connector-kafka) provides a source/destination for Apache Kafka.
* [Postgres connector](https://github.com/ConduitIO/conduit-connector-postgres) provides a source/destination for PostgreSQL.
* [S3 connector](https://github.com/ConduitIO/conduit-connector-s3) provides a source/destination for AWS S3.
* [Generator connector](https://github.com/ConduitIO/conduit-connector-generator) provides a source which generates random data (useful for testing).

Besides these connectors there is a number of standalone connectors that can be added to Conduit as plugins (find the complete list [here](https://github.com/ConduitIO/conduit/blob/main/docs/connectors.md)).

#### Standalone Connector Binary

To install a standalone connector you first need the compiled connector binary. A binary can normally be downloaded from the latest release in the connector's GitHub repository (this may vary in 3rd party connectors not developed by the Conduit team). Make sure to download the binary that matches your operating system and architecture.

Alternatively you can build the binary yourself (for instructions on building a connector please refer to the readme of that specific connector).

### Installing a Connector in Conduit

Conduit loads standalone connectors at startup. The connector binaries need to be placed in the `connectors` directory relative to the Conduit binary so Conduit can find them. Alternatively, the path to the standalone connectors can be adjusted using the CLI flag `-connectors.path`, for example:

```shell
./conduit -connectors.path=/path/to/connectors/
```

Names of the connector binaries are not important, since Conduit is getting the information about connectors from connectors themselves (using their gRPC API).

Find out how to reference your connector.
