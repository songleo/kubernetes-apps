```
kubectl apply --server-side -f manifests/setup
kubectl wait \
	--for condition=Established \
	--all CustomResourceDefinition \
	--namespace=monitoring
kubectl apply -f manifests/

k port-forward svc/prometheus-k8s 9090:9090

http://localhost:9090/alerts
```

### ref

- https://github.com/prometheus-operator/kube-prometheus/tree/release-0.13
