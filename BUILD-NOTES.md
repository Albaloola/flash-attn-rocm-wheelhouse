# Build notes

Artifact:

- `flash_attn-2.8.4-cp312-cp312-linux_x86_64.whl`

Build environment:

- Python `3.12`
- torch `2.11.0+rocm7.2`
- torchvision `0.26.0+rocm7.2`
- HIP `7.2.26015`
- GPU `AMD Radeon RX 7900 XTX`
- GPU arch `gfx1100`
- platform `Linux x86_64`

Build commands used:

```bash
pip install torch torchvision --index-url https://download.pytorch.org/whl/rocm7.2
pip install ninja packaging
git clone https://github.com/ROCm/flash-attention.git
cd flash-attention
export GPU_ARCHS="gfx1100"
pip install . --no-build-isolation
```

Source repo used:

- repo: `https://github.com/ROCm/flash-attention`
- build targeted to `gfx1100`

Suggested install:

```bash
pip install ./flash_attn-2.8.4-cp312-cp312-linux_x86_64.whl --no-deps
```

Compatibility warning:

- This is not an officially published universal ROCm wheel.
- Treat it as a targeted community build for the matrix above unless broader testing proves otherwise.
