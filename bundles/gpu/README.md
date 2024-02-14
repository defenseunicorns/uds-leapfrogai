# LeapfrogAI UDS GPU-Enabled Deployment

## Disclaimer

`llama-cpp-python-gpu` **_WILL NOT_** run if GPU resources are unavailable to the pod(s). You must provide sufficient NVIDIA GPU scheduling or else the pod(s) will go into a crash loop.

`whisper` can run without without GPU scheduling - just turn off the `GPU_ENABLED` boolean.

## Testing

In order to test the GPU deployment locally on K3d, use the following command when deploying UDS-Core:

```bash
 uds deploy k3d-core-istio-dev:0.12.0 --set K3D_EXTRA_ARGS="--gpus=1 --image=ghcr.io/justinthelaw/k3d-gpu-support:v1.27.4-k3s1-cuda"
```
