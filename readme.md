# Test & Analytics Kafka Consumer for Mapp DataStreams

## Configuration

The project uses an `application.properties` file to configure the java application. The configuration file needs to be
provided when running the app on console.

Please find an example of the properties file in `./dist` folder.

To complete the config add the following - sensitive - information provided by Mapp:

```
consumer-group=***TBD***
topic=***TBD***
username=***TBD***
password=***TBD***
```

Additionally, the following advanced settings can be adjusted to meet the individual needs:

```
poll-timeout=1000
max-partition-fetch_bytes=1048576
max-poll-records=1000 (Kafka default: 500)
```

## Run

A runnable - fat - jar is provided in the `./dist` folder.

To run the test application simply navigate into the `./dist` folder and run:

```
java -jar webtrekk-data-streams-consumer-test.jar ./application.properties
```

## Logging for test & analytics

### TSV (tab separated values) logging

Setting `enable-tsv-logs` to `true` will enable additional logging to 2 TSV files:

- meta.tsv:
- records:tsv:

Hit: The files are overwritten on every start of the application.

### Kafka Client Logs

Setting `enable-kafka-client-debug-logs` to `true` will enable additional debug logs of the Kafka consumer on console.

## Build it

The project uses maven assembly plugin to build a runnable - fat - jar containing all dependencies.

Use `mvn package` on project root to build the jar. The jar will be located in the `./target/` folder of the project.
