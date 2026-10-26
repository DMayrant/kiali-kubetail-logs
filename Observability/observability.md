# Prometheus/Grafana 🔭
```bash
kubectl create ns monitor 

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

helm repo update

kubectl label namespace monitor istio-injection=enabled --overwrite

helm install my-prometheus prometheus-community/prometheus --version 29.37.2 -n monitor
```
# Set GP2 As Default 
```bash 
kubectl annotate storageclass gp2 \
  storageclass.kubernetes.io/is-default-class="true" --overwrite
  ```