# GPU Deployment Command for UDS Core

```bash
 uds deploy k3d-core-istio-dev:0.12.0 --set K3D_EXTRA_ARGS="--gpus=1 --image=ghcr.io/justinthelaw/k3d-gpu-support:v1.27.4-k3s1-cuda"
```
