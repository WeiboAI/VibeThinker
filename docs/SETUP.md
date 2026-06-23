# Setup Guide

## Prerequisites

- Python 3.10+
- CUDA-capable GPU (recommended for inference)
- 8GB+ VRAM for VibeThinker-3B, 4GB+ for VibeThinker-1.5B (bfloat16)

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/OMCHOKSI108/VibeThinkerModel.git
cd VibeThinkerModel
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate  # Linux/macOS
# or
venv\Scripts\activate  # Windows
```

### 3. Install dependencies

**Minimal (transformers only):**

```bash
pip install transformers>=4.54.0
```

**With inference engine (recommended):**

```bash
pip install transformers>=4.54.0 vllm==0.10.1
# or
pip install transformers>=4.54.0 sglang>=0.4.9.post6
```

**Full (with additional dependencies for evaluation):**

```bash
pip install transformers>=4.54.0 torch datasets accelerate
```

### 4. Download model weights

If you do not want to download weights on first run, you can pre-download:

```bash
# From Hugging Face
pip install huggingface_hub
huggingface-cli download WeiboAI/VibeThinker-3B
# or from the mirror
huggingface-cli download OMCHOKSI108/VibeThinker-3B
```

> **Note:** Model weights are approximately 6GB for VibeThinker-3B. Ensure sufficient disk space.

## Verify Installation

Run a quick sanity check:

```python
from transformers import AutoModelForCausalLM, AutoTokenizer
model = AutoModelForCausalLM.from_pretrained(
    "WeiboAI/VibeThinker-3B",
    low_cpu_mem_usage=True,
    torch_dtype="bfloat16",
    device_map="auto"
)
tokenizer = AutoTokenizer.from_pretrained("WeiboAI/VibeThinker-3B", trust_remote_code=True)
print(f"Model loaded: {model.config._name_or_path}")
```

## Docker (optional)

Not provided. You can use a standard PyTorch inference Docker image:

```bash
docker pull pytorch/pytorch:2.5.0-cuda12.4-cudnn9-runtime
```

## Notebooks

A starter Jupyter notebook is available in [`notebooks/`](../notebooks/):

- [`vibethinker-inference.ipynb`](../notebooks/vibethinker-inference.ipynb) — load model, run inference, custom prompts
- [`notebooks/README.md`](../notebooks/README.md) — overview and usage guide

Run the notebook after completing the setup steps above.
