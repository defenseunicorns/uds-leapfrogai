# LeapfrogAI UDS GPU-Enabled Deployment

## Prerequisites

- [K3D](https://k3d.io/)
- [UDS CLI](https://github.com/defenseunicorns/uds-cli)

## Disclaimers

GPU workloads **_WILL NOT_** run if GPU resources are unavailable to the pod(s). You must provide sufficient NVIDIA GPU scheduling or else the pod(s) will go into a crash loop.

`whisper` can run without without GPU scheduling - just turn off the `GPU_ENABLED` boolean.

If `vllm` is being used with:

- A quantized model, then `QUANTIZATION` must be set to the quantization method (e.g., `awq`, `gptq`, etc.)
- Tensor parallelism for spreading a model's heads across multiple GPUs, then `TENSOR_PARALLEL_SIZE` must be set to an integer value that:
  a) falls within the number of GPU resources (`nvidia.com/gpu`) that are allocatable in the cluster
  b) divisible by the number of attention heads in the model architecture (if number of heads is 32, then `TENSOR_PARALLEL_SIZE` could be 2, 4, etc.)

These `vllm` specific environment variables must be set at the model skeleton level or when the model is deployed into the cluster.

## Testing

In order to test the GPU deployment locally on K3d, use the following command when deploying UDS-Core:

```bash
 uds create .
 uds deploy k3d-core-slim-dev:0.18.0 --set K3D_EXTRA_ARGS="--gpus=all --image=ghcr.io/justinthelaw/k3d-gpu-support:v1.27.4-k3s1-cuda"
 uds deploy uds-bundle-leapfrogai-*.tar.zst --confirm
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
