# Splunk Custom Helm Chart

This Helm chart is designed to deploy Splunk in a Kubernetes environment. It provides configurations to customize the deployment according to your needs.

## References

Docker image used from dockerhub splunk/splunk repository:
https://hub.docker.com/layers/splunk/splunk/9.1.3-patch1/images/sha256-12985957c5095e0440b286ec08df2c6a4315599c69c55c202f44fe7d8aa120ca?context=explore

Docker deployment reference:
https://docs.splunk.com/Documentation/Splunk/9.2.1/Installation/DeployandrunSplunkEnterpriseinsideDockercontainers

## Installation of docker container

To install the Splunk Helm chart, run the following command:

```bash
docker pull splunk/splunk:9.1.3-patch1
docker run -d -p 8000:8000 -e SPLUNK_START_ARGS='--accept-license' -e SPLUNK_PASSWORD='<password>' splunk/splunk:9.1.3-patch1
docker ps -a -f id=<container_id>
localhost:8000
```


## Authors

- [@SushilSanjayBhile](https://github.com/SushilSanjayBhile)

