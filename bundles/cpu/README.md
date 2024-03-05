# CPU-Based UDS Deployment of AI for National Security

## Prerequisites

- K3D
- UDS CLI
- Zarf

## Instructions

```
uds deploy k3d-core-istio-dev:0.14.1

uds create .

uds deploy <package name>
```

## Checking Deployment

| Tool | URL |
| --- | --- |
| UI | <https://ai.uds.dev> |
| API | <https://leapfrogai-api.uds.dev> |

## References

- [UDS-Core](https://github.com/defenseunicorns/uds-core)
