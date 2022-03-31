FROM openjdk:17-alpine

RUN apk --update add ca-certificates bash

ADD https://repo1.maven.org/maven2/io/opentelemetry/contrib/opentelemetry-jmx-metrics/1.11.0-alpha/opentelemetry-jmx-metrics-1.11.0-alpha.jar /opt/opentelemetry-jmx-metrics.jar

ENTRYPOINT ["/opt/openjdk-17/bin/java"]
CMD [ \
    "-Dotel.jmx.service.url=service:jmx:rmi:///jndi/rmi://kafka:1099/jmxrmi", \
    "-Dotel.jmx.target.system=kafka", \
    "-Dotel.metrics.exporter=otlp", \
    "-Dotel.exporter.otlp.endpoint=http://otel-collector:4317", \
    "-jar", \
    "/opt/opentelemetry-jmx-metrics.jar" \
]