# Standard RoPE: Frequencies

The frequencies $\theta_i$ in Standard RoPE are not arbitrary. They follow an exponentially decaying geometric progression, which ensures that different dimensions capture positional information at different scales.

## Frequency Definition
The base frequency is typically set to 10,000. For a $d$-dimensional embedding, the frequencies are calculated as:
$$ \theta_i = 10000^{-2(i-1)/d}, \quad i \in \{1, 2, \dots, d/2\} $$

This means that:
- Small $i$ (early dimensions) have high frequencies, allowing them to capture fine-grained positional changes.
- Large $i$ (later dimensions) have low frequencies, capturing long-range dependencies.

## SVG Diagram: Frequency Decay
<svg width="400" height="200" viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Axis -->
  <line x1="50" y1="150" x2="350" y2="150" stroke="black" stroke-width="2" />
  <line x1="50" y1="150" x2="50" y2="50" stroke="black" stroke-width="2" />
  <text x="180" y="180">Dimension Index (i)</text>
  <text x="10" y="100" transform="rotate(-90, 20, 100)">Frequency (θ)</text>
  
  <!-- Curve -->
  <path d="M 50 60 Q 150 140 350 145" fill="none" stroke="purple" stroke-width="3" />
  
  <!-- Labels -->
  <text x="60" y="55" fill="purple">High Frequency (Fine-grained)</text>
  <text x="250" y="140" fill="purple">Low Frequency (Coarse)</text>
</svg>

[Back to README](../README.md)
