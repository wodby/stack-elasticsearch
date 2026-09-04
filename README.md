# Elasticsearch application stack for Kubernetes on Wodby

Deploy Elasticsearch applications on Kubernetes with Wodby.

This repository defines the Wodby stack manifests and default service
composition for Elasticsearch.

<!-- wodby:generated:start -->

## Stack contract

- [Elasticsearch stack on Wodby](https://wodby.com/stacks/elasticsearch)
- [Browse Wodby application stacks](https://wodby.com/stacks)
- [Wodby stack documentation](https://wodby.com/docs/2.0/stacks/)
- [Stack manifest reference](https://wodby.com/docs/2.0/stacks/template/)

## Service definitions

- [Elasticsearch service](https://github.com/wodby/service-elasticsearch)
- [Kibana service](https://github.com/wodby/service-kibana)

## What's included

| Component / service | Default configuration |
| --- | --- |
| Elasticsearch<br>`elasticsearch` | required; enabled by default; volumes: `data` 20 GB |
| Kibana<br>`kibana` | optional; enabled by default; links: `elasticsearch` → `elasticsearch` |

Enabled optional services are selected by default but can be excluded when an
app is created. Disabled optional services are available but not selected by
default. Required services cannot be excluded.

## Validate the stack manifest

```bash
wodby stack validate-manifest stack.yml --org <org-id>
```

<!-- wodby:generated:end -->

## Authentication

Elasticsearch initializes the internal `kibana_system` account, and the stack
passes its generated password to Kibana through the required service link. Sign
in to Kibana as `elastic` using the Elasticsearch service's generated
`password` token.
