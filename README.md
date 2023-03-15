# code-with-quarkus

This project uses Quarkus, the Supersonic Subatomic Java Framework.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./gradlew quarkusDev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application

The application can be packaged using:
```shell script
./gradlew build
```
It produces the `quarkus-run.jar` file in the `build/quarkus-app/` directory.
Be aware that it’s not an _über-jar_ as the dependencies are copied into the `build/quarkus-app/lib/` directory.

The application is now runnable using `java -jar build/quarkus-app/quarkus-run.jar`.

If you want to build an _über-jar_, execute the following command:
```shell script
./gradlew build -Dquarkus.package.type=uber-jar
```

The application, packaged as an _über-jar_, is now runnable using `java -jar build/*-runner.jar`.

## Creating a native executable

You can create a native executable using: 
```shell script
./gradlew build -Dquarkus.package.type=native
```

Or, if you don't have GraalVM installed, you can run the native executable build in a container using: 
```shell script
./gradlew build -Dquarkus.package.type=native -Dquarkus.native.container-build=true
```

You can then execute your native executable with: `./build/code-with-quarkus-1.0.0-SNAPSHOT-runner`

If you want to learn more about building native executables, please consult https://quarkus.io/guides/gradle-tooling.

## Related Guides

- Camel Weather ([guide](https://camel.apache.org/camel-quarkus/latest/reference/extensions/weather.html)): Poll the weather information from Open Weather Map
- Reactive MySQL client ([guide](https://quarkus.io/guides/reactive-sql-clients)): Connect to the MySQL database using the reactive pattern
- Camel MyBatis ([guide](https://camel.apache.org/camel-quarkus/latest/reference/extensions/mybatis.html)): Performs a query, poll, insert, update or delete in a relational database using MyBatis
- Camel Debezium MySQL Connector ([guide](https://camel.apache.org/camel-quarkus/latest/reference/extensions/debezium-mysql.html)): Capture changes from a MySQL database
- Camel AWS 2 MQ ([guide](https://camel.apache.org/camel-quarkus/latest/reference/extensions/aws2-mq.html)): Manage AWS MQ instances using AWS SDK version 2.x
- Camel Timer ([guide](https://camel.apache.org/camel-quarkus/latest/reference/extensions/timer.html)): Generate messages in specified intervals using java.util.Timer
- Camel Jackson ([guide](https://camel.apache.org/camel-quarkus/latest/reference/extensions/jackson.html)): Marshal POJOs to JSON and back using Jackson
