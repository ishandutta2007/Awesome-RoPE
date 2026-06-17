# NTK-aware RoPE

NTK-aware RoPE is a technique used to extend the context window of LLMs without requiring extensive retraining. It was first proposed by a community member on Reddit and later formalized.

## The Problem
Standard RoPE performance degrades quickly when the sequence length exceeds the context window seen during training. This is because the model encounters unseen high-frequency rotations.

## The Solution
NTK-aware RoPE applies a non-linear scaling to the base frequency. Instead of scaling all frequencies equally, it scales the base $\theta$ itself. This preserves the information in high-frequency dimensions (which capture local structure) while compressing the low-frequency dimensions (which capture global structure).

The modified base becomes $\theta' = \theta \cdot s^{d/(d-2)}$, where $s$ is the scaling factor.

## SVG Diagram: Non-linear Scaling
<svg width="400" height="200" viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Comparison Curves -->
  <path d="M 50 60 Q 150 140 350 145" fill="none" stroke="gray" stroke-width="2" stroke-dasharray="5,5" />
  <text x="300" y="160" fill="gray">Standard</text>
  
  <path d="M 50 60 Q 150 120 350 130" fill="none" stroke="red" stroke-width="3" />
  <text x="300" y="120" fill="red">NTK-aware</text>
  
  <text x="60" y="40" fill="black">High frequencies preserved</text>
</svg>

[Back to README](../README.md)
