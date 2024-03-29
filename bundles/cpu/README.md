# CPU Bundle for LeapfrogAI

## Prerequisites

- [K3D](https://k3d.io/)
- [UDS CLI](https://github.com/defenseunicorns/uds-cli)

## Instructions

``` bash
uds deploy k3d-core-slim-dev:0.18.0
uds create .
uds deploy <bundle name> # from last step
```

## Checking Deployment

Inspect the cluster using:

``` bash
uds zarf tools monitor
```

| Tool | URL |
| --- | --- |
| UI | <https://ai.uds.dev> |
| API | <https://leapfrogai-api.uds.dev/docs> |
| RAG Server | <https://leapfrogai-rag.uds.dev/docs> |

## References

- [UDS-Core](https://github.com/defenseunicorns/uds-core)
