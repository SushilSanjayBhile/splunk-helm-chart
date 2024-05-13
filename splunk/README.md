# Splunk Custom Helm Chart

This Helm chart is designed to deploy Splunk in a Kubernetes environment. It provides configurations to customize the deployment according to your needs.

## Prerequisites

Before deploying this Helm chart, ensure the following prerequisites are met:

- Kubernetes cluster is up and running.
- Helm is installed and configured on your Kubernetes cluster.
- Access to the Splunk Enterprise Docker image. You can obtain it from the official Splunk website or Docker Hub.

## Installation

To install the Splunk Helm chart, run the following command:

```bash
helm install splunk ./splunk-custom-chart
Replace ./splunk-custom-chart with the path to the directory containing the Helm chart.

Configuration
The following table lists the configurable parameters of the Splunk Helm chart and their default values:

Parameter	Description	Default
image.repository	Splunk Enterprise Docker image repository	splunk/splunk
image.tag	Splunk Enterprise Docker image tag	latest
image.pullPolicy	Image pull policy	IfNotPresent
splunkPassword	Admin password for Splunk	changeme
splunkLicenseMaster	URL for Splunk Enterprise license master	nil
splunkIndexerReplicas	Number of indexer replicas	1
splunkSearchHeadReplicas	Number of search head replicas	1
persistence.enabled	Enable persistence for Splunk data	true
persistence.storageClassName	Storage class for persistent volume	standard
persistence.accessMode	Access mode for persistent volume	ReadWriteOnce
persistence.size	Size of persistent volume	10Gi
resources	CPU/Memory resource requests/limits	{}
service.type	Kubernetes service type	ClusterIP
service.port	Service port for accessing Splunk	8000
ingress.enabled	Enable ingress for accessing Splunk	false
ingress.annotations	Ingress annotations	{}
ingress.hosts	Ingress hosts	[]
ingress.tls	Ingress TLS configuration	[]
Specify each parameter using the --set key=value[,key=value] argument to helm install, or provide a custom values.yaml file.

Accessing Splunk
Once the Splunk deployment is successful, you can access the Splunk web interface using the following steps:

Find the nodes external IP address, make sure 30800 node-port is open to http requests:
bash
kubectl get nodes -owide
Open a web browser and navigate to http://<node-ip>:30800/

Log in using the default credentials:

Username: admin
Password: The password specified in the SPLUNK_PASSWORD parameter in values.yaml file.
```


## Authors

- [@SushilSanjayBhile](https://github.com/SushilSanjayBhile)


