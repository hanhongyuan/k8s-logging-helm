# k8s-logging-helm
Setting up elk based logging stack in K8S cluster with helm(3)

Main features of the helm chart
# Can be scaled from minikube up to production scaled setups
# Supports optional kafka ingestion point for scaled setups
# Supports external managed EL stack
# ELK stack can be easilly upgraded
# Supports node affinity and pod-antiaffinity rules for HA statefulsets

For easy access to the kibana UI in minikube:
# Expose the kibana service as LB servicetype
```kubectl expose svc/elk-kibana --name elk-kibana-lb --type=LoadBalancer --port 5601 --target-port=5601```
# Start minikube tunnel and check the elk-kibana-lb LoadBalancer Service IP
```minikube tunnel```
# Open a browser at http://<elk-kibana-lb IP>:5601


Note: minikube needs default-storageclass and storage-provisioner addons

To install:
helm install elk <path to k8s-logging-helm chart>
