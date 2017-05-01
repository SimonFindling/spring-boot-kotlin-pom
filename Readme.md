
# Spring Boot Kotlin Parent POM
A Spring Boot 2.0.0.BUILD-SNAPSHOT parent POM with Kotlin language support. 
It has also docker container support through the docker plugin configuration in the parent pom.
## Maven Properties
You can overwrite the following properties:

Property | Description
---------|------------
kotlin.compiler.incremental | Adds incremental compiler support. Currently experimental, by default `true`.
kotlin.version | The Kotlin language version. Currently `1.1.2`.

## Parent POM
This project uses a Spring Boot 2.0.0.BUILD-SNAPSHOT parent POM, that can be found [here](https://github.com/SimonFindling/spring-boot-docker-pom).

## Jetbrains kotlin-maven-plugin
The Jetbreans kotlin-maven-plugin introduces kotlin support for maven.

### Configuration
The project uses two compiler plugins: `spring` and `jpa`. The `spring` plugin introduces Spring support
and the `jpa` plugin handles the (needed) default constructor generation for classes, that are annotated
with `@Entity`.

Also the JVM Target version needs to be specified. By default it is `1.8` and it can be changed through the
`java.version` property. But Spring Boot 2.0.0 needs Java 8, therefore it is not recommended to use a lower version.

### Plugin Execution
The execution of the plugin is bound to the goals `compile` respectively `test-compile`.