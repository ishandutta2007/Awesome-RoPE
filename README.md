# Awesome-RoPE
## Rotary Position Embedding (RoPE) Variants

Rotary Position Embedding (RoPE) encodes positional information by applying a rotation in a 2D complex plane. It pairs dimensions of the Query and Key vectors and rotates them by an angle proportional to the token's position, preserving relative distances regardless of absolute placement.

## 1. Standard RoPE (Base RoPE)
* **Definition:** The original RoFormer method introduced by Su et al. (2021). 
* **Mechanism:** It divides high-dimensional token vectors into 2D chunks and multiplies each chunk by a 2D rotation matrix. 
* **Frequencies:** The rotation angles are based on exponentially decaying geometric frequencies.
* **Core Benefit:** Attention scores depend entirely on the relative distance between tokens, improving language modeling.

## 2. Context Extension Variants
Standard base frequencies lose accuracy or hit limits during massive context windows. These variants scale frequencies to handle longer inputs:
* **NTK-aware RoPE (Neural Tangent Kernel):** Down-scales frequencies of early dimensions while leaving high-frequency dimensions alone to compress long sequences without retraining.
* **YaRN (Yet another RoPE for Networks):** Extends context limits (e.g., 128k+ tokens) using RoPE interpolation and an NTK-scaling factor to recover lost performance with minimal fine-tuning.
* **Linear Interpolation RoPE (PI):** Linearly compresses position indices to fit longer texts into the model's originally trained context window.

## 3. Modality & Architectural Adaptations
* **2D RoPE:** Adapts 1D text embedding into a 2D plane for Vision Transformers (ViTs) to capture horizontal and vertical coordinate shifts independently.
* **VRoPE (Video RoPE):** Adds a third temporal dimension to the rotation for frame sequence tracking in Video-LLMs.
* **Circle-RoPE:** Decoupled rotary embeddings for Large Vision-Language Models to better handle aspect ratio changes and multi-resolution visual inputs.

## 4. Advanced & Parameterized Variants
* **ComRoPE:** Uses learnable commuting angle matrices instead of strict fixed sinusoidal frequencies, allowing the model to adaptively learn optimal positional intervals.
* **Context-aware RoPE:** Dynamically adjusts rotational angles based on semantic content or token importance to focus more on contextually heavy phrases.
