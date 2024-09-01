# Developer Environment Setup

## JDK Installation using SDKMAN
I highly recommend using [SDKMAN](https://sdkman.io/) for installing JDK, Maven, Gradle, etc.

```shell
$ curl -s "https://get.sdkman.io" | bash
$ source "$HOME/.sdkman/bin/sdkman-init.sh"
$ sdk list java
$ sdk install java 21.0.1-tem
$ sdk install maven
$ sdk install gradle
```

Create `.sdkmanrc` file in the project root directory and specify tool versions as follows:

```
java=21.0.1-tem
maven=3.9.9
gradle=8.10
```

Now, you can run `sdk env install` to install all the tools specified 
in the `.sdkmanrc` file and activate those versions in the current terminal session.

You can also add the following property in `$HOME/.sdkman/etc/config` file to automatically 
activate the tool versions specified in the `.sdkmanrc` file when `cd` into that directory.

```shell
sdkman_auto_env=true
```

Verify the installation

```shell
$ java -version
openjdk version "21.0.1" 2023-10-17 LTS
OpenJDK Runtime Environment Temurin-21.0.1+12 (build 21.0.1+12-LTS)
OpenJDK 64-Bit Server VM Temurin-21.0.1+12 (build 21.0.1+12-LTS, mixed mode)

$ mvn --version

$ gradle --version
```

## Docker
Follow your OS specific installation instructions for Docker Desktop at
https://docs.docker.com/desktop/

After installation, verify `docker` and `docker compose` is installed successfully.

```shell
$ docker info
Client:
 Version:    27.0.3
 Context:    desktop-linux
 ...
 ...
Server:
 Server Version: 27.0.3
 ...
 ...

$ docker compose version
Docker Compose version v2.28.1-desktop.1
```

### Alternatives to Docker Desktop
* [Podman](https://podman.io/)
* [OrbStack](https://orbstack.dev/) for MacOS only

To make Podman works well with Java frameworks and libraries, you need to configure certain things.
Follow [Podman Desktop for Java Development](https://www.thomasvitale.com/podman-desktop-for-java-development/) to configure Podman.

## Intellij IDEA
IntelliJ IDEA is a powerful IDE for developing Java(JVM) based applications.

You can download IntelliJ IDEA and install from https://www.jetbrains.com/idea/download/.
But a better approach is using [JetBrains Toolbox](https://www.jetbrains.com/toolbox-app/).
From JetBrains Toolbox, you can install any of the JetBrains IDEs and update them easily.

## LocalStack Desktop
[LocalStack](https://www.localstack.cloud/) is a cloud software development framework 
to develop and test your AWS applications locally.

You can install [LocalStack Desktop](https://docs.localstack.cloud/user-guide/tools/localstack-desktop/) 
or use [Testcontainers](https://testcontainers.com/guides/testing-aws-service-integrations-using-localstack/) to run LocalStack instances.

## Install Ollama
Download Ollama installer for your OS at https://ollama.com/.

Once installed and started the service, go to terminal and pull/run the models:

```shell
$ ollama help
$ ollama pull llama3.1 
$ ollama run llama3.1 
$ ollama run gemma2
$ ollama list
$ ollama ps
```

## Common Utilities
* [jq](https://jqlang.github.io/jq/download/)
* [httpie](https://httpie.io/)
* [go-task](https://taskfile.dev/)
