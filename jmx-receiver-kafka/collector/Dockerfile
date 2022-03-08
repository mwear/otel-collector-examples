FROM openjdk:17-alpine

RUN apk --update add ca-certificates bash

ADD https://github.com/open-telemetry/opentelemetry-collector-releases/releases/download/v0.45.0/otelcol-contrib_0.45.0_linux_amd64.tar.gz /
RUN tar -xzf otelcol-contrib_0.45.0_linux_amd64.tar.gz
RUN chmod 755 /otelcol-contrib

ADD https://repo1.maven.org/maven2/io/opentelemetry/contrib/opentelemetry-jmx-metrics/1.11.0-alpha/opentelemetry-jmx-metrics-1.11.0-alpha.jar /opt/opentelemetry-jmx-metrics.jar

ENTRYPOINT ["/otelcol-contrib"]
CMD ["--config", "/etc/otelcol-contrib/config.yaml"]
EXPOSE 4317 55678 55679