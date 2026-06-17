# Awesome-RoPE
## Rotary Position Embedding (RoPE) Variants

Rotary Position Embedding (RoPE) encodes positional information by applying a rotation in a 2D complex plane. It pairs dimensions of the Query and Key vectors and rotates them by an angle proportional to the token's position, preserving relative distances regardless of absolute placement.

## 1. Standard RoPE (Base RoPE)
| Feature | Description | Year | Paper Link |
| :--- | :--- | :--- | :--- |
| **Definition** | The original RoFormer method introduced by Su et al. | 2021 | [arXiv:2104.09864](https://arxiv.org/abs/2104.09864) |
| **Mechanism** | Divides high-dimensional token vectors into 2D chunks and multiplies each chunk by a 2D rotation matrix. | 2021 | [arXiv:2104.09864](https://arxiv.org/abs/2104.09864) |
| **Frequencies** | The rotation angles are based on exponentially decaying geometric frequencies. | 2021 | [arXiv:2104.09864](https://arxiv.org/abs/2104.09864) |
| **Core Benefit** | Attention scores depend entirely on the relative distance between tokens, improving language modeling. | 2021 | [arXiv:2104.09864](https://arxiv.org/abs/2104.09864) |

## 2. Context Extension Variants
Standard base frequencies lose accuracy or hit limits during massive context windows. These variants scale frequencies to handle longer inputs:

| Variant | Description | Year | Paper Link |
| :--- | :--- | :--- | :--- |
| **NTK-aware RoPE** | Down-scales frequencies of early dimensions while leaving high-frequency dimensions alone to compress long sequences without retraining. | 2023 | [Reddit Proposal](https://www.reddit.com/r/LocalLLaMA/comments/14lz77b/ntkaware_scaled_rope_allows_llama_models_to_have/) |
| **YaRN** | Extends context limits (e.g., 128k+ tokens) using RoPE interpolation and an NTK-scaling factor to recover lost performance with minimal fine-tuning. | 2023 | [arXiv:2309.00071](https://arxiv.org/abs/2309.00071) |
| **Linear Interpolation RoPE (PI)** | Linearly compresses position indices to fit longer texts into the model's originally trained context window. | 2023 | [arXiv:2306.15595](https://arxiv.org/abs/2306.15595) |

## 3. Modality & Architectural Adaptations
| Variant | Description | Year | Paper Link |
| :--- | :--- | :--- | :--- |
| **2D RoPE** | Adapts 1D text embedding into a 2D plane for Vision Transformers (ViTs) to capture horizontal and vertical coordinate shifts independently. | 2024 | [arXiv:2403.13298](https://arxiv.org/abs/2403.13298) |
| **VRoPE (Video RoPE)** | Adds a third temporal dimension to the rotation for frame sequence tracking in Video-LLMs. | 2025 | [arXiv:2502.11664](https://arxiv.org/abs/2502.11664) |
| **Circle-RoPE** | Decoupled rotary embeddings for Large Vision-Language Models to better handle aspect ratio changes and multi-resolution visual inputs. | 2025 | [arXiv:2505.16416](https://arxiv.org/abs/2505.16416) |

## 4. Advanced & Parameterized Variants
| Variant | Description | Year | Paper Link |
| :--- | :--- | :--- | :--- |
| **ComRoPE** | Uses learnable commuting angle matrices instead of strict fixed sinusoidal frequencies, allowing the model to adaptively learn optimal positional intervals. | 2025 | [arXiv:2506.03737](https://arxiv.org/abs/2506.03737) |
| **Context-aware RoPE** | Dynamically adjusts rotational angles based on semantic content or token importance to focus more on contextually heavy phrases. | 2025 | [arXiv:2507.23083](https://arxiv.org/abs/2507.23083) |
