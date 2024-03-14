# CPU-Based UDS Deployment of AI for National Security

## Prerequisites

- [K3D](https://k3d.io/)
- [UDS CLI](https://github.com/defenseunicorns/uds-cli)

## Instructions

```bash
uds deploy k3d-core-istio-dev:0.14.1

uds create .

uds deploy <package name>
```

## Checking Deployment

Inspect the cluster using:

```bash
uds zarf tools monitor
```

| Tool       | URL                                   |
| ---------- | ------------------------------------- |
| UI         | <https://ai.uds.dev>                  |
| API        | <https://leapfrogai-api.uds.dev/docs> |
| RAG Server | <https://leapfrogai-rag.uds.dev/docs> |

## References

- [UDS-Core](https://github.com/defenseunicorns/uds-core)
