# Monitoring resources
[Helm Prometheus stack Values file](https://github.com/prometheus-community/helm-charts/blob/main/charts/kube-prometheus-stack/values.yaml)
## Loki
[TechnoTim Meet Grafana LOKI](https://technotim.live/posts/grafana-loki/)

[Helm Loki Values file](https://github.com/grafana/loki/blob/main/production/helm/loki/values.yaml)  
Also see:  
[simple-scalable-values.yaml](https://github.com/grafana/loki/blob/main/production/helm/loki/simple-scalable-values.yaml) and 
[single-binary-values.yaml](https://github.com/grafana/loki/blob/main/production/helm/loki/single-binary-values.yaml)
Do not look into Loki Stack as this has not been updated and does not work with later versions of Loki

[Loki Helmchart Configuraion reference](https://grafana.com/docs/loki/latest/setup/install/helm/reference/)

### S3 Configuration
[A bit about distributed Loki Stack](https://akyriako.medium.com/kubernetes-logging-with-grafana-loki-promtail-in-under-10-minutes-d2847d526f9e)  

[s3 Sniplet configuration](https://grafana.com/docs/loki/latest/configure/examples/configuration-examples/#10-expanded-s3-snippetyaml)  
Be aware this configuration is for the configuration file. NOT the helm chart. see 
[Loki Release](./loki-release.yaml) for usage.  

### Retention
[Configure Compactor retention](https://grafana.com/docs/loki/latest/operations/storage/retention/)  
remember to enable the compactor deployment.

### Promtail
[Helm Promtail Values file](https://github.com/grafana/helm-charts/blob/main/charts/promtail/values.yaml)  
[Scraping configurations Journald](https://grafana.com/docs/loki/latest/send-data/promtail/scraping/#journal-scraping-linux-only)  

### Event exporter
[Event exporter loki config](https://github.com/resmoio/kubernetes-event-exporter/blob/master/README.md#loki)  
Would be nice if it supportet templated labels like AWS EventBridge. But it does not...

### Flux events
[Pod Monitoring](https://github.com/fluxcd/flux2-monitoring-example/blob/main/monitoring/configs/podmonitor.yaml)  
[Kube State Metric Values](https://github.com/fluxcd/flux2-monitoring-example/blob/main/monitoring/controllers/kube-prometheus-stack/kube-state-metrics-config.yaml)  
[Dashboards](https://github.com/fluxcd/flux2-monitoring-example/tree/main/monitoring/configs/dashboards)  