# ES cluster

```This repository was created in Azure DevOps and moved here just to document it```

---
## Elasticsearch
This repository contains configuration of ElasticSearch cluster with coordinating, master-only and data-only nodes.
Coordinator and master nodes are responsible for managing request to ES and redirecting them to data nodes. This setup allows to unburden data nodes and let them focus on data processing.
Configuration was configured for and tested in 3 nodes environment

## Traefik
Traefik as reverse proxy is responsible for applying SSL certificates loadbalancing incoming traffic to master nodes. URLs are created by the environment variables.

Endpoints:\
Kibana: ```http://${KIBANA_URL}``` \
Elasticsearch: ```http://${ELASTICSEARCH_URL}```


## Filebeat
Filebeat sends logs to ES cluster. Only ElasticSearch and Filebeat's logs are included with seperate index.

## References
[Azure DevOps](https://dev.azure.com/K0nicki/Projects/_git/ElasticSearch?fbclid=IwAR2wPCDfJLG6--O_WUGAWK6mxQB9iZ9NjTJE1ny_NwEgR8TFS0Siu21LJQQ)\
[Pipeline](https://dev.azure.com/K0nicki/Projects/_build?definitionId=16)
