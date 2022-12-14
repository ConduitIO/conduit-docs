# Local Machine

## Deploying Conduit on your Machine

Before you get started, you will need to decide on which method of installation you want. Conduit can be installed via:

1. Binary Download (Recommended)
2. Docker
3. Building from source

### Binary Download (Recommended)

Start by downloading the binary for the [latest release](https://github.com/ConduitIO/conduit/releases/latest) on Conduit's Release page. Make sure that you pick the installation that matches the architecture of your machine. Conduit does have nightly releases. If new features exist that aren't yet in a supported version, you'll need to go to the [releases page](https://github.com/ConduitIO/conduit/releases) to find the appropriate nightly release. The Conduit team does its best to make sure nightly releases are deployable.

Using an M1 Mac and Conduit v0.2.1 as an example, find the binary that matches `Darwin_arm64` and download that to your machine. Once it's downloaded to your machine, expand the file and then start Conduit:

```shell
$ tar zxvf conduit_0.2.1_Darwin_arm64.tar.gz
$ ./conduit
```

### Docker

[Docker](https://docs.docker.com/) enables you to run Conduit as in a container. Conduit's Docker images are hosted on [GitHub](https://github.com/ConduitIO/conduit/pkgs/container/conduit). You can find the `Dockerfile` [here](https://github.com/ConduitIO/conduit/blob/main/Dockerfile).

After you install Docker, you can pull the Conduit image by running the following command:

```shell
$ docker pull ghcr.io/conduitio/conduit:latest
```

Then, you can run Conduit by running the following command:

```shell
$ docker run -d -p 8080:8080 ghcr.io/conduitio/conduit
```

**Helpful Tip:** If you're using Docker, check out [Watchtower](https://containrrr.dev/watchtower/). After we push an update, Watchtower will keep your Conduit container updated by gracefully shutting down your existing container and restarting it with the same options used when initially deployed.

### Building from source

Before you can build Conduit from source, you need to have Go 1.18 or higher installed. The Go website has [comprehensive instructions](https://go.dev/doc/install) on how to get the language installed on your machine. Once installed, you can follow the rest of the instructions.

1. Start by downloading the source code from the latest stable release on the Conduit [Releases Page](https://github.com/ConduitIO/conduit/releases/latest). Alternatively, you can run this command to automatically download the latest stable source to your current directory:

```shell
$ TAG=$(curl -s https://api.github.com/repos/ConduitIO/conduit/releases/latest | grep "tag_name\": \"v[0-9.]*" | awk -F \" '/tag_name\": \"*\"/{print $(NF-1)}') && curl -o conduit.tgz -L https://github.com/ConduitIO/conduit/tarball/$TAG
```

A file called `conduit.tgz` will be in your current directory. The next step is to expand the source:

```shell
$ tar zxvf conduit.tgz
```

Then change directories to the appropriate folder. Keep in mind that the folder name might be different between releases since it's tied to the latest git sha for the commit.

```shell
$ cd ConduitIO-
```

Now build the project:

```shell
$ make
```

If you want to build conduit without the UI, instead of running `make`, you can run the following command:

```shell
$ make build-server
```

You will have a new binary built for your architecture and machine. All that's left is to run it!

```shell
./conduit
```
