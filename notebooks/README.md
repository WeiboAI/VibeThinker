# Notebooks — VibeThinker

This directory contains Jupyter notebooks for experimenting with VibeThinker models locally.

## Available Notebooks

| Notebook | Description |
|----------|-------------|
| [`vibethinker-inference.ipynb`](vibethinker-inference.ipynb) | Starter notebook for loading VibeThinker-3B with transformers and running inference |

## Planned Notebooks

- **VibeThinker-3B Inference** — Load the model with `transformers` and run example prompts
- **Prompt Examples** — Math, coding, and STEM reasoning prompts with expected output patterns
- **Hardware Benchmarking** — Memory usage, inference speed, and quantization notes
- **Hugging Face Hub Integration** — Loading from HF, using with `pipeline`, and sharing results

## Usage

All notebooks assume you have:
1. Installed dependencies (`transformers>=4.54.0`, `torch`, etc.)
2. Access to a CUDA-capable GPU with sufficient VRAM
3. Downloaded or configured access to the model weights

See [`docs/SETUP.md`](../docs/SETUP.md) for installation instructions and [`docs/INFERENCE.md`](../docs/INFERENCE.md) for inference parameters.

## Safe Local Testing

Notebooks use only publicly available model weights from WeiboAI or the OMCHOKSI108 mirror. No API keys, tokens, or secrets are required. All inference runs locally on your hardware.

## Attribution

Model weights and original code belong to **WeiboAI and contributors**. See [`docs/ATTRIBUTION.md`](../docs/ATTRIBUTION.md) for full credits.
