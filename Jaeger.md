Jaeger
======

docker-compose 
--------------
  jaeger_cadastro: 
    container_name: jaeger_cadastro
    image: jaegertracing/all-in-one:1.6
    ports: 
    - "5775:5775/udp"
    - "6831:6831/udp"
    - "6832:6832/udp"
    - "5778:5778"
    - "16686:16686"
    - "14268:14268"
    - "9411:9411"

CLI 
---
./mvnw quarkus:add-extensions -Dextensions="opentracing"

application.properties
----------------------
quarkus.jaeger.service-name=jaeger-cadastro
quarkus.jaeger.sampler-type=const
quarkus.jaeger.sampler-param=1
quarkus.jaeger.endpoint=http://localhost:14268/api/traces

Hibernate - Tracig dependency (https://github.com/opentracing-contrib/java-jdbc/tree/master)
---------------------------------------------------------------------------------------------
    <dependency>
      <groupId>io.opentracing.contrib</groupId>
      <artifactId>opentracing-jdbc</artifactId>
    </dependency>
	

application.properties
----------------------
quarkus.datasource.jdbc.url=jdbc:tracing:postgresql://localhost:5432/postgres
quarkus.datasource.jdbc.driver=io.opentracing.contrib.jdbc.TracingDriver
quarkus.datasource.username=broker
quarkus.datasource.password=broker


Classe de Negócio -> @Traced() 


Prometheus 
==========

Criar Imagem sobrescrevendo - Dockerfile.prometheus (https://prometheus.io/docs/prometheus/latest/installation/)
----------------------------------------------------
FROM prom/prometheus:v2.49.1
ADD prometheus.yml /etc/prometheus/ 

                              
Criar Imagem sobrescrevendo - prometheus.yml (https://github.com/prometheus/prometheus/blob/main/documentation/examples/prometheus.yml)
--------------------------------------------							  
							  
# my global config
global:
  scrape_interval: 15s # Set the scrape interval to every 15 seconds. Default is every 1 minute.
  evaluation_interval: 15s # Evaluate rules every 15 seconds. The default is every 1 minute.
  # scrape_timeout is set to the global default (10s).

# Alertmanager configuration
alerting:
  alertmanagers:
    - static_configs:
        - targets:
          # - alertmanager:9093

# Load rules once and periodically evaluate them according to the global 'evaluation_interval'.
rule_files:
  # - "first_rules.yml"
  # - "second_rules.yml"

# A scrape configuration containing exactly one endpoint to scrape:
# Here it's Prometheus itself.
scrape_configs:
  # The job name is added as a label `job=<job_name>` to any timeseries scraped from this config.
  - job_name: "prometheus"

    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.

    static_configs:
      - targets: ["localhost:9090"]

  - job_name: "prometheus-cadastro"

    # metrics_path defaults to '/metrics'
    # scheme defaults to 'http'.
    scrape_interval: 5s # Set the scrape interval to every 15 seconds. Default is every 1 minute.
    static_configs:
     - targets: ["localhost:8080"]
	 

Build 
-----
docker build -f Dockerfile.prometheus -t prometheus-cadastro .

(**  docker images | grep prom) 











