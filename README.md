# Quarkus-JReleaser

This project uses JReleaser to Release a simple Quarkus CLI app. 

To learn more about JReleaser, please visit: https://jreleaser.org/
If you want to learn more about Quarkus, please visit: https://quarkus.io/
Finally, if you want to learn more about how to use JReleaser specifically with Quarkus project, please visit: https://quarkus.io/guides/jreleaser . 

## Packaging and running the application

The application can be packaged as a native executable using:
```shell script
./mvnw -Pnative,dist package
```

The application is now runnable using `./target/quarkus-jreleaser*-runner* <yourname>`.

If you want to learn more about building native executables, please consult https://quarkus.io/guides/maven-tooling.

## Releasing the application with Jreleaser
You can generate a changelog with

```shell script
./mvnw -Prelease jreleaser:changelog
```

A release dry run can be run like so:

```shell script
./mvnw -Prelease jreleaser:full-release -Djreleaser.select.current.platform -Djreleaser.dry.run=true
```

And finally, you can do an actual release with

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
