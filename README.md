# Quarkus-JReleaser

This project uses JReleaser to Release a simple Quarkus CLI app. 

To learn more about JReleaser, please visit: https://jreleaser.org/
If you want to learn more about Quarkus, please visit: https://quarkus.io/
Finally, if you want to learn more about how to use JReleaser specifically with Quarkus project, please visit: https://quarkus.io/guides/jreleaser . 

## Prerequisites
To run this example, you need:

JDK 11+ installed with JAVA_HOME configured appropriately

Apache Maven 3.8.8+

Optionally Mandrel or GraalVM installed and configured appropriately if you want to build a native executable (or Docker if you use a native container build)

a GitHub account and a GitHub Personal Access token

## Packaging and running the application

The application can be packaged as a native executable using:
```shell script
./mvnw -Pnative,dist package
```

The application is now runnable using `./target/quarkus-jreleaser*-runner* <yourname>`.

If you want to learn more about building native executables, please consult https://quarkus.io/guides/maven-tooling.

## Releasing the application with JReleaser

Set a `JRELEASER_GITHUB_TOKEN` environment variable with a github token that has write access to your repository.

Inspect the pom.xml and update with your name, github url etc.  

### Generate a changelog

You can generate a changelog with

```shell script
./mvnw -Prelease jreleaser:changelog
```

### Release Dry run

A release dry run can be run like so:

```shell script
./mvnw -Prelease jreleaser:full-release -Djreleaser.select.current.platform -Djreleaser.dry.run=true
```

### Release to Github

And finally, you can do an actual release with:

```shell script
./mvnw -Prelease jreleaser:full-release -Djreleaser.select.current.platform
```

## Related Guides

- Picocli ([guide](https://quarkus.io/guides/picocli)): Develop command line applications with Picocli

## Provided Code

### Picocli Example

Hello and goodbye are civilization fundamentals. Let's not forget it with this example picocli application by changing the <code>command</code> and <code>parameters</code>.

[Related guide section...](https://quarkus.io/guides/picocli#command-line-application-with-multiple-commands)

Also for picocli applications the dev mode is supported. When running dev mode, the picocli application is executed and on press of the Enter key, is restarted.

As picocli applications will often require arguments to be passed on the commandline, this is also possible in dev mode via:
```shell script
./mvnw compile quarkus:dev -Dquarkus.args='Quarky'
```
