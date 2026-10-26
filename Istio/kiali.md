# Istio 🎛️
```bash
kubectl label namespace nginx istio-injection=enabled --overwrite

kubectl get ns -L istio-injection 

helm uninstall istio-base istio/base -n istio-system 
```

# Kiali for Istio Performance Observability 🔭

```bash
helm repo add kiali https://kiali.org/helm-charts

helm install my-kiali-server kiali/kiali-server --version 2.33.0 -n istio-system

helm upgrade my-kiali-server kiali/kiali-server \
  --namespace istio-system \
  --version 2.33.0 \
  --reuse-values \
  --set external_services.prometheus.enabled=true \
  --set-string external_services.prometheus.url=http://my-prometheus-server.monitor.svc.cluster.local:80

kubectl get svc -n istio-system 
kubectl create token kiali -n istio-system
```