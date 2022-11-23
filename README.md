# Getting Started

Conduit is a data integration tool for software engineers. Its purpose is to help you move data from A to B. You can use Conduit to send data from Kafka to Postgres, between files and APIs, between [supported connectors](https://github.com/ConduitIO/conduit/blob/main/docs/connectors.md), and any datastore you can build a plugin for.

It's written in [GoLang](https://go.dev/), compiles to a binary, and is designed to be easy to use and [deploy](https://docs.conduit.io/docs/Deploy/overview).

To get started:

1. [Download the latest Conduit release](https://github.com/ConduitIO/conduit/releases/latest).
2. Unzip:

If you're on Mac, it will look something like this:

```shell
tar zxvf conduit_0.3.0_Darwin_x86_64.tar.gz
```

1. Start Conduit:

```shell
./conduit
```

**Tip**: Depending on your operating system, you may need to run `chmod +x conduit` before running the binary.

1. Navigate to `http://localhost:8080` to check Conduit's UI:
2. Build Pipelines 🚀.
