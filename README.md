# Lexicast — Proprietary Semantic PCIe Transport Engine

**Copyright © 2026 Leonardo Leon (Bergrisar). All Rights Reserved.**  
*Confidential & Proprietary.*

## Project Overview
**Lexicast** is an asymmetric, low-latency semantic transport architecture designed to bypass PCIe bottlenecks between System RAM and GPU VRAM during AI inference.

### Validated Roadmap & Results (NVIDIA GTX 1060 3GB)
* **v0.1 – v0.3:** Initial proofs of concept, TorchScript JIT integration, and segmented `.lex` lexicon building achieving up to **100%** cosine similarity on structured tensors.
* **v0.4 (Entropy Diagnostic):** First real-world test on **Qwen2.5-0.5B** MLP weights (`16-D` codebook), revealing accuracy drops (`84.24%`) on high-entropy neural layers.
* **v0.4.1 (4-D L2 Codebook Optimization):** Implemented a `1.00 MB` L2-resident 4-dimensional codebook (`8:1` compression), pushing LLM inference fidelity to **99.4474%** and a **1.26x** speedup (`23.326 ms` vs `29.413 ms`) with **0.00 ms** runtime training.

*(Benchmark visualizations for v0.1 through v0.4.1 are available in the repository source).*

## Development Roadmap
- [x] **v0.1:** Initial PyTorch Proof of Concept.
- [x] **v0.2:** TorchScript JIT and L2 micro-tiling.
- [x] **v0.3:** Segmented `.lex` lexicon builder.
- [x] **v0.4 & v0.4.1:** Real-world LLM weight compression (`Qwen2.5-0.5B`, `99.45%` fidelity).
- [ ] **v0.5:** Multi-layer LLM token generation prototype & native C++/CUDA fused kernel SDK.
