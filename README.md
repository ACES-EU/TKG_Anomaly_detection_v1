# TKG Anomaly detection

## Steps

1) Benchmark App deployment
   
   The online boutique app was deployed in a local Kubernetes cluster

   Details here: (https://github.com/GoogleCloudPlatform/microservices-demo)
   
2) Data collection

Using Istio and Prometheus, time series data about microservices calls was collected (ms, total requests, request delay, request size, error codes )
   
3) TKG generation

   Raphtory library was used for temporal graphs
   
4) Anomaly detection

   Traditional ML algorithms were trained to build models for binary classification (normal and abnormal). The labels were added based on error codes on ms calls
