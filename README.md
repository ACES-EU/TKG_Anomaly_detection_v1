# TKG Anomaly detection

## Steps

1) Benchmark App deployment
   
   The online boutique app was deployed in a local Kubernetes cluster

   Details here: (https://github.com/GoogleCloudPlatform/microservices-demo)
   
2) Data collection

Using Istio and Prometheus, time series data about microservices calls was collected (ts, ms source, ms destination,  total requests, request delay, request size, and error codes)

Data is collected via direct connection to prometheus (prom = PrometheusConnect(url ="http://raphtory03:9090", disable_ssl=True))

   Raphtory3 is one of our local servers

   We can collect real-time and historical data providing a start and an end date.

   An example of collected data is added to this repo

3) TKG generation

   Raphtory library was used to generate temporal graphs in a time window.
   
4) Anomaly detection

   Traditional ML algorithms were trained to build models for binary classification (normal and abnormal). The labels were added based on error codes on ms calls.
