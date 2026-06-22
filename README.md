# flash-attn ROCm wheelhouse

Community-built `flash-attn` wheels for Linux AMD/ROCm setups that do not have convenient prebuilt binaries available.

Current release:

- `flash_attn-2.8.4-cp312-cp312-linux_x86_64.whl`
- source repo used for the build: `ROCm/flash-attention`
- Python: `3.12`
- torch: `2.11.0+rocm7.2`
- torchvision: `0.26.0+rocm7.2`
- HIP: `7.2.26015`
- tested GPU / arch: `AMD Radeon RX 7900 XTX / gfx1100`
- platform: `Linux x86_64`

## Install

```bash
pip install \
  "https://github.com/example-user/flash-attn-rocm-wheelhouse/releases/download/v2.8.4-rocm7.2-gfx1100-cp312/flash_attn-2.8.4-cp312-cp312-linux_x86_64.whl" \
  --no-deps
```

Install compatible ROCm PyTorch first:

```bash
pip install torch torchvision --index-url https://download.pytorch.org/whl/rocm7.2
```

This wheel was built from the ROCm fork using:

```bash
pip install ninja packaging
git clone https://github.com/ROCm/flash-attention.git
cd flash-attention
export GPU_ARCHS="gfx1100"
pip install . --no-build-isolation
```

## SHA256

See [SHA256SUMS.txt](./SHA256SUMS.txt).

## Notes

- This is a community build, not an official upstream release.
- The wheel filename is the standard upstream wheel name; the ROCm and GPU matrix is documented in the release notes and this README.
- This build was created inside a Voicebox backend virtual environment, but the wheel itself is for `flash_attn`, not for Voicebox specifically.
- The wheel should be treated as a targeted community build for the matrix above, not as a universal ROCm wheel.

## Licensing

This repository redistributes a wheel built from the ROCm fork of `flash-attention`. Please follow the upstream project license and notices:

- source repo used for the build: https://github.com/ROCm/flash-attention
- upstream package metadata inside the wheel reports the upstream project and BSD license classification
