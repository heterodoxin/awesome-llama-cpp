
<p align="center">
  <a href="https://github.com/ggml-org/llama.cpp">
    <img src="https://raw.githubusercontent.com/CypherpunkSamurai/awesome-llama-cpp/refs/heads/master/assets/llamacpp.png" alt="llama.cpp logo" width="300">
  </a>
</p>

<h1 align="center">Awesome LLaMa.cpp</h1>

<p align="center">
  <b>A curated, exhaustively-researched catalog of llama.cpp forks, derivative projects, and experimental branches.</b>
</p>

<p align="center">
  <a href="https://github.com/ggml-org/llama.cpp">
    <img src="https://img.shields.io/github/stars/ggml-org/llama.cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/ggml-org/llama.cpp">
    <img src="https://img.shields.io/github/forks/ggml-org/llama.cpp?style=social" alt="GitHub forks">
  </a>
  <a href="https://github.com/ggml-org/llama.cpp/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/ggml-org/llama.cpp" alt="License">
  </a>
  <a href="https://github.com/topics/turboquant?l=c%2B%2B&o=desc&s=forks">
    <img src="https://img.shields.io/badge/topic-turboquant-blue" alt="TurboQuant topic">
  </a>
</p>

---

## Table of Contents

- [Overview](#overview)
- [The Original](#the-original)
- [TurboQuant & MTP Forks](#turboquant--mtp-forks)
- [Hardware-Specific Forks](#hardware-specific-forks)
- [Performance & Quantization Forks](#performance--quantization-forks)
- [Model & Feature Extensions](#model--feature-extensions)
- [Language Bindings & Ecosystem](#language-bindings--ecosystem)
- [How to Discover More Forks](#how-to-discover-more-forks)

---

## Overview

This document tracks notable forks of **[ggml-org/llama.cpp](https://github.com/ggml-org/llama.cpp)** and closely related TurboQuant/MTP branches. The focus is on:

- **TurboQuant** and **Multi-Token Prediction (MTP)** forks
- **Hardware-specific** forks (ROCm, Vulkan, AMD GPUs, NVIDIA DGX)
- **Performance / quantization** forks
- **Model-specific** forks for unique architectures

---

## The Original

### [ggml-org/llama.cpp](https://github.com/ggml-org/llama.cpp)

<p>
  <a href="https://github.com/ggml-org/llama.cpp">
    <img src="https://img.shields.io/github/stars/ggml-org/llama.cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/ggml-org/llama.cpp">
    <img src="https://img.shields.io/github/last-commit/ggml-org/llama.cpp" alt="Last commit">
  </a>
  <a href="https://github.com/ggml-org/llama.cpp/blob/master/LICENSE">
    <img src="https://img.shields.io/github/license/ggml-org/llama.cpp" alt="License">
  </a>
</p>

The authoritative source for llama.cpp. LLM inference in pure C/C++ with minimal setup and state-of-the-art performance on a wide range of hardware. Created by Georgi Gerganov in March 2023.

**Key Features:**
- Pure C/C++ implementation with no external dependencies
- Apple Silicon first-class support via Metal (MPS)
- CUDA, ROCm (HIP), Vulkan, and SYCL backends
- GGUF format for efficient model storage
- **Native MTP support** (merged in 2026) for Qwen 3.6 and DeepSeek models
- Server mode with OpenAI-compatible API

---

## TurboQuant & MTP Forks

These forks implement extreme KV cache compression (TurboQuant) and/or Multi-Token Prediction (MTP) for significant throughput improvements.

### [AtomicBot-ai/atomic-llama-cpp-turboquant](https://github.com/AtomicBot-ai/atomic-llama-cpp-turboquant)

<p>
  <a href="https://github.com/AtomicBot-ai/atomic-llama-cpp-turboquant">
    <img src="https://img.shields.io/github/stars/AtomicBot-ai/atomic-llama-cpp-turboquant?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/AtomicBot-ai/atomic-llama-cpp-turboquant">
    <img src="https://img.shields.io/github/last-commit/AtomicBot-ai/atomic-llama-cpp-turboquant" alt="Last commit">
  </a>
</p>

llama.cpp fork with TurboQuant WHT-rotated KV cache & weight compression + Gemma 4 MTP and Qwen 3.6 NextN speculative decoding (+30-50% throughput).

**Features:**
- TurboQuant WHT-rotated KV cache compression
- Gemma 4 MTP speculative decoding
- Qwen 3.6 NextN speculative decoding
- 30-50% throughput improvement

---

### [TheTom/llama-cpp-turboquant](https://github.com/TheTom/llama-cpp-turboquant)

<p>
  <a href="https://github.com/TheTom/llama-cpp-turboquant">
    <img src="https://img.shields.io/github/stars/TheTom/llama-cpp-turboquant?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/TheTom/llama-cpp-turboquant">
    <img src="https://img.shields.io/github/last-commit/TheTom/llama-cpp-turboquant" alt="Last commit">
  </a>
</p>

The original TurboQuant implementation by TheTom. LLM inference in C/C++ with TurboQuant KV cache quantization enabling massive context windows on limited VRAM.

**Features:**
- Turbo3/Turbo4 KV cache quantization
- WHT-rotated KV cache compression
- Metal and CUDA support

---

### [atomicmilkshake/llama-cpp-turboquant](https://github.com/atomicmilkshake/llama-cpp-turboquant)

<p>
  <a href="https://github.com/atomicmilkshake/llama-cpp-turboquant">
    <img src="https://img.shields.io/github/stars/atomicmilkshake/llama-cpp-turboquant?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/atomicmilkshake/llama-cpp-turboquant">
    <img src="https://img.shields.io/github/last-commit/atomicmilkshake/llama-cpp-turboquant" alt="Last commit">
  </a>
</p>

llama.cpp fork with TurboQuant quantization (turbo2/3/4) and TriAttention GPU-accelerated KV cache pruning. Achieves 75 tok/s on Qwen3-8B with RTX 3080.

**Features:**
- TurboQuant custom quantization (turbo2/3/4)
- TriAttention GPU-accelerated KV cache pruning
- Hardware-optimized CUDA kernels

---

### [Indras-Mirror/llama.cpp-turboq-mtp](https://github.com/Indras-Mirror/llama.cpp-turboq-mtp)

<p>
  <a href="https://github.com/Indras-Mirror/llama.cpp-turboq-mtp">
    <img src="https://img.shields.io/github/stars/Indras-Mirror/llama.cpp-turboq-mtp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/Indras-Mirror/llama.cpp-turboq-mtp">
    <img src="https://img.shields.io/github/last-commit/Indras-Mirror/llama.cpp-turboq-mtp" alt="Last commit">
  </a>
</p>

Fused TBQ4 Flash Attention + MTP + Shared Tensors for llama.cpp. Achieves 82+ tok/s with TurboQuant and MTP combined. Includes context checkpoints for MTP slots.

**Features:**
- Fused TurboQuant Flash Attention
- Multi-Token Prediction integration
- Shared tensors optimization
- Context checkpoints support

---

### [destroyor/llama.cpp-mtp-turboquant-vulkan](https://github.com/destroyor/llama.cpp-mtp-turboqutant-vulkan)

<p>
  <a href="https://github.com/destroyor/llama.cpp-mtp-turboqutant-vulkan/">
    <img src="https://img.shields.io/github/stars/destroyor/llama.cpp-mtp-turboqutant-vulkan?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/destroyor/llama.cpp-mtp-turboqutant-vulkan/">
    <img src="https://img.shields.io/github/last-commit/destroyor/llama.cpp-mtp-turboqutant-vulkan" alt="Last commit">
  </a>
</p>

Vulkan-centric fork combining TurboQuant and MTP. Achieves 1.37x-1.56x MTP acceleration ratio with full quality pass (no UTF-8 issues, no token repetition).

**Features:**
- Vulkan backend optimization
- TurboQuant + MTP combination
- Draft cache recommendations for different context sizes

---

### [pp1840/turboquant-llama-lab](https://github.com/pp1840/turboquant-llama-lab)

<p>
  <a href="https://github.com/pp1840/turboquant-llama-lab">
    <img src="https://img.shields.io/github/stars/pp1840/turboquant-llama-lab?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/pp1840/turboquant-llama-lab">
    <img src="https://img.shields.io/github/last-commit/pp1840/turboquant-llama-lab" alt="Last commit">
  </a>
</p>

Experimental TurboQuant implementation and llama.cpp-style integration path for research purposes.

**Features:**
- Experimental TurboQuant implementations
- Benchmark utilities
- Configuration testing

---

### [TheTom/turboquant_plus](https://github.com/TheTom/turboquant_plus)

<p>
  <a href="https://github.com/TheTom/turboquant_plus">
    <img src="https://img.shields.io/github/stars/TheTom/turboquant_plus?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/TheTom/turboquant_plus">
    <img src="https://img.shields.io/github/last-commit/TheTom/turboquant_plus" alt="Last commit">
  </a>
</p>

Experimental integration and research workspace for TurboQuant-related work targeting llama.cpp. Contains codec design, calibration, and validation papers.

**Features:**
- TurboQuant research workspace
- Comparison tools for implementations
- Documentation and getting started guides

---

## Hardware-Specific Forks

### [iacopPBK/llama.cpp-gfx906](https://github.com/iacopPBK/llama.cpp-gfx906)

<p>
  <a href="https://github.com/iacopPBK/llama.cpp-gfx906">
    <img src="https://img.shields.io/github/stars/iacopPBK/llama.cpp-gfx906?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/iacopPBK/llama.cpp-gfx906">
    <img src="https://img.shields.io/github/last-commit/iacopPBK/llama.cpp-gfx906" alt="Last commit">
  </a>
</p>

Optimized for AMD GFX906-class GPUs (MI50/MI60/Vega7). Tested with ROCm 7.1.1. Includes "poor man's FlashAttention" implementation and power scaling scripts.

**Features:**
- AMD GFX906 (MI50/MI60/Vega7) optimizations
- Wave64 kernels
- Power scaling with overclocking scripts

---

### [croll83/llama.cpp-dgx](https://github.com/croll83/llama.cpp-dgx)

<p>
  <a href="https://github.com/croll83/llama.cpp-dgx">
    <img src="https://img.shields.io/github/stars/croll83/llama.cpp-dgx?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/croll83/llama.cpp-dgx">
    <img src="https://img.shields.io/github/last-commit/croll83/llama.cpp-dgx" alt="Last commit">
  </a>
</p>

llama.cpp fork optimized for NVIDIA DGX Spark / GB10 (Blackwell, SM 12.1). Runtime for hybrid Qwen3.5/3.6 / Qwopus 27B-class models on 128GB unified memory.

**Features:**
- NVIDIA DGX Spark / GB10 optimization
- NVFP4 quantization
- DFlash MTP support
- TurboQuant weights + KV cache

---

### [antirez/llama.cpp-deepseek-v4-flash](https://github.com/antirez/llama.cpp-deepseek-v4-flash)

<p>
  <a href="https://github.com/antirez/llama.cpp-deepseek-v4-flash">
    <img src="https://img.shields.io/github/stars/antirez/llama.cpp-deepseek-v4-flash?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/antirez/llama.cpp-deepseek-v4-flash">
    <img src="https://img.shields.io/github/last-commit/antirez/llama.cpp-deepseek-v4-flash" alt="Last commit">
  </a>
</p>

Experimental implementation of DeepSeek V4 Flash in llama.cpp by Salvatore Sanfilippo (antirez, creator of Redis). OpenAI API compatible HTTP server.

**Features:**
- DeepSeek V4 Flash support
- OpenAI API compatible server
- Multi-user parallel decoding

---

### [carlosfundora/llama.cpp-1-bit-turbo](https://github.com/carlosfundora/llama.cpp-1-bit-turbo)

<p>
  <a href="https://github.com/carlosfundora/llama.cpp-1-bit-turbo">
    <img src="https://img.shields.io/github/stars/carlosfundora/llama.cpp-1-bit-turbo?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/carlosfundora/llama.cpp-1-bit-turbo">
    <img src="https://img.shields.io/github/last-commit/carlosfundora/llama.cpp-1-bit-turbo" alt="Last commit">
  </a>
</p>

HIP/ROCm fork optimized for AMD RDNA2 (gfx1030) with PrismML Q1_0_G128 1-bit quant support, RotorQuant, TurboQuant, EAGLE3 and P-EAGLE speculative decoding.

**Features:**
- AMD RDNA2 (RX 6000/7000) optimization
- PrismML Q1_0_G128 1-bit quantization
- RotorQuant KV cache compression
- EAGLE3/P-EAGLE speculative decoding

---

### [invisiofficial/rk-llama.cpp](https://github.com/invisiofficial/rk-llama.cpp)

<p>
  <a href="https://github.com/invisiofficial/rk-llama.cpp">
    <img src="https://img.shields.io/github/stars/invisiofficial/rk-llama.cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/invisiofficial/rk-llama.cpp">
    <img src="https://img.shields.io/github/last-commit/invisiofficial/rk-llama.cpp" alt="Last commit">
  </a>
</p>

llama.cpp fork with Rockchip NPU integration for RK3588 devices (Orange Pi, etc.). CPU + NPU hybrid inference.

**Features:**
- Rockchip RK3588 NPU support
- Orange Pi optimization
- IOMMU domain management
- Caching system

---

## Performance & Quantization Forks

### [ikawrakow/ik_llama.cpp](https://github.com/ikawrakow/ik_llama.cpp)

<p>
  <a href="https://github.com/ikawrakow/ik_llama.cpp">
    <img src="https://img.shields.io/github/stars/ikawrakow/ik_llama.cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/ikawrakow/ik_llama.cpp">
    <img src="https://img.shields.io/github/last-commit/ikawrakow/ik_llama.cpp" alt="Last commit">
  </a>
</p>

llama.cpp fork with better CPU and hybrid GPU/CPU performance, new SOTA quantization types, first-class Bitnet support, better DeepSeek support.

**Features:**
- New SOTA quantization types (IQ series)
- Better CPU and hybrid GPU/CPU performance
- First-class BitNet b1.58 support
- FlashMLA and fused MoE operations

---

### [elizaOS/llama.cpp](https://github.com/elizaOS/llama.cpp)

<p>
  <a href="https://github.com/elizaOS/llama.cpp">
    <img src="https://img.shields.io/github/stars/elizaOS/llama.cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/elizaOS/llama.cpp">
    <img src="https://img.shields.io/github/last-commit/elizaOS/llama.cpp" alt="Last commit">
  </a>
</p>

Milady-controlled llama.cpp fork: TurboQuant + QJL + PolarQuant + DFlash unified. Used by ElizaOS agent framework.

**Features:**
- TurboQuant integration
- QJL (Quantized Johnson-Lindenstrauss) support
- PolarQuant implementation
- DFlash unified support

---

### [Anbeeld/beellama.cpp](https://github.com/Anbeeld/beellama.cpp)

<p>
  <a href="https://github.com/Anbeeld/beellama.cpp">
    <img src="https://img.shields.io/github/stars/Anbeeld/beellama.cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/Anbeeld/beellama.cpp">
    <img src="https://img.shields.io/github/last-commit/Anbeeld/beellama.cpp" alt="Last commit">
  </a>
</p>

DFlash & TurboQuant in llama.cpp with up to 3x faster generation and 7.5x more KV cache in same VRAM. Performance-focused fork for local GGUF inference.

**Features:**
- DFlash speculative decoding
- TurboQuant/TCQ KV cache compression
- Up to 3x faster generation
- 7.5x more KV cache in same VRAM

---

## Model & Feature Extensions

### [heterodoxin/AbliteratedOutTheBox](https://github.com/heterodoxin/AbliteratedOutTheBox)

<p>
  <a href="https://github.com/heterodoxin/AbliteratedOutTheBox">
    <img src="https://img.shields.io/github/stars/heterodoxin/AbliteratedOutTheBox?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/heterodoxin/AbliteratedOutTheBox">
    <img src="https://img.shields.io/github/last-commit/heterodoxin/AbliteratedOutTheBox" alt="Last commit">
  </a>
</p>

A fork that removes model refusals at inference time with a gated projection hook, no fine-tuning and no separate abliterated model. It reads the refusal direction from each prompt and edits only when a gate fires, leaving other prompts bit-identical to the base model.

**Features:**
- Inference-time abliteration via a hook at the build_cvec layer-output site
- Fit-free: per-prompt directions, no training and no extra files
- Architecture-universal, works on any llama.cpp-supported model

---

### [Mintplex-Labs/prism-ml-llama.cpp](https://github.com/Mintplex-Labs/prism-ml-llama.cpp)

<p>
  <a href="https://github.com/Mintplex-Labs/prism-ml-llama.cpp">
    <img src="https://img.shields.io/github/stars/Mintplex-Labs/prism-ml-llama.cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/Mintplex-Labs/prism-ml-llama.cpp">
    <img src="https://img.shields.io/github/last-commit/Mintplex-Labs/prism-ml-llama.cpp" alt="Last commit">
  </a>
</p>

LLM inference in C/C++ with changes from Prism-ML to support 1Bit models. Fork synced to main llama.cpp repo.

**Features:**
- PrismML 1-bit model support
- Bonsai model family support
- Synced with main llama.cpp

---

### [jina-ai/llama.cpp](https://github.com/jina-ai/llama.cpp)

<p>
  <a href="https://github.com/jina-ai/llama.cpp">
    <img src="https://img.shields.io/github/stars/jina-ai/llama.cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/jina-ai/llama.cpp">
    <img src="https://img.shields.io/github/last-commit/jina-ai/llama.cpp" alt="Last commit">
  </a>
</p>

Jina AI's fork with modifications for neural search and multimodal embeddings. Includes fixes for jina-embeddings-v4 support.

**Features:**
- Multimodal embedding support
- jina-embeddings-v4 integration
- Neural search optimizations

---

### [ymcki/llama.cpp-b4139](https://github.com/ymcki/llama.cpp-b4139)

<p>
  <a href="https://github.com/ymcki/llama.cpp-b4139">
    <img src="https://img.shields.io/github/stars/ymcki/llama.cpp-b4139?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/ymcki/llama.cpp-b4139">
    <img src="https://img.shields.io/github/last-commit/ymcki/llama.cpp-b4139" alt="Last commit">
  </a>
</p>

A fork of llama.cpp that can convert and run Llama-3_1-Nemotron-51B and DeciLM-7B-Instruct.

**Features:**
- Llama-3.1-Nemotron-51B support
- DeciLM-7B-Instruct compatibility
- Custom model layout handling

---

### [brave-experiments/llama.cpp-public](https://github.com/brave-experiments/llama.cpp-public)

<p>
  <a href="https://github.com/brave-experiments/llama.cpp-public">
    <img src="https://img.shields.io/github/stars/brave-experiments/llama.cpp-public?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/brave-experiments/llama.cpp-public">
    <img src="https://img.shields.io/github/last-commit/brave-experiments/llama.cpp-public" alt="Last commit">
  </a>
</p>

llama.cpp fork with customisations for MELT. Maintained by Brave for internal experimentation.

**Features:**
- Brave MELT framework integration
- Internal experimentation branch

---

### [WisdomShell/llama_cpp_for_codeshell](https://github.com/WisdomShell/llama_cpp_for_codeshell)

<p>
  <a href="https://github.com/WisdomShell/llama_cpp_for_codeshell">
    <img src="https://img.shields.io/github/stars/WisdomShell/llama_cpp_for_codeshell?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/WisdomShell/llama_cpp_for_codeshell">
    <img src="https://img.shields.io/github/last-commit/WisdomShell/llama_cpp_for_codeshell" alt="Last commit">
  </a>
</p>

CodeShell model in C/C++. Specialized fork optimized for CodeShell code-generation models.

**Features:**
- CodeShell model support
- Code completion optimizations

---

### [nomic-ai/llama.cpp](https://github.com/nomic-ai/llama.cpp)

<p>
  <a href="https://github.com/nomic-ai/llama.cpp">
    <img src="https://img.shields.io/github/stars/nomic-ai/llama.cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/nomic-ai/llama.cpp">
    <img src="https://img.shields.io/github/last-commit/nomic-ai/llama.cpp" alt="Last commit">
  </a>
</p>

Nomic AI's fork created for their GPT4All project. One of the earliest significant forks.

**Features:**
- GPT4All integration
- Early llama.cpp modifications

---

## Language Bindings & Ecosystem

### [abetlen/llama-cpp-python](https://github.com/abetlen/llama-cpp-python)

<p>
  <a href="https://github.com/abetlen/llama-cpp-python">
    <img src="https://img.shields.io/github/stars/abetlen/llama-cpp-python?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/abetlen/llama-cpp-python">
    <img src="https://img.shields.io/github/last-commit/abetlen/llama-cpp-python" alt="Last commit">
  </a>
</p>

Simple Python bindings for llama.cpp. High-level Python API for text completion and OpenAI compatible web server.

**Features:**
- High-level Python API
- OpenAI compatible web server
- Simple pip installation

---

### [elizaOS/node-llama-cpp](https://github.com/elizaOS/node-llama-cpp)

<p>
  <a href="https://github.com/elizaOS/node-llama-cpp">
    <img src="https://img.shields.io/github/stars/elizaOS/node-llama-cpp?style=social" alt="GitHub stars">
  </a>
  <a href="https://github.com/elizaOS/node-llama-cpp">
    <img src="https://img.shields.io/github/last-commit/elizaOS/node-llama-cpp" alt="Last commit">
  </a>
</p>

Run LLMs locally on your machine. Metal, CUDA and Vulkan support. Pre-built binaries provided with fallback to building from source.

**Features:**
- Node.js bindings
- Pre-built binaries
- Metal, CUDA, Vulkan support
- Native TypeScript support

---

## How to Discover More Forks

### GitHub Topic Search

- **TurboQuant forks:**  
  <https://github.com/topics/turboquant?l=c%2B%2B&o=desc&s=forks>

- **llama-cpp topic:**  
  <https://github.com/topics/llama-cpp?l=c%2B%2B&o=desc&s=forks>

### Web Searches

```
site:github.com "llama.cpp" turboquant
site:reddit.com "llama.cpp" "turboquant"
site:x.com "atomic-llama-cpp-turboquant"
site:news.ycombinator.com llama.cpp turboquant
```

---

## Contributing

To keep this document useful:

1. Add a new entry in the appropriate section
2. Include repository link and one sentence explaining the focus
3. Optional: link to Reddit/X/HN post explaining or benchmarking the fork
4. Open a pull request

---

<p align="center">
  <i>Last updated: May 2026</i><br>
  <i>Maintained by the community</i>
</p>
