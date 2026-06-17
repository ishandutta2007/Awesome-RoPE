# 2D RoPE

2D RoPE is an adaptation of Rotary Position Embeddings for two-dimensional data, primarily used in Vision Transformers (ViTs).

## The Concept
In 1D RoPE, we rotate based on a single position index $m$. In 2D RoPE, we have two indices: $m_x$ for the horizontal position and $m_y$ for the vertical position.
The embedding vector is typically split into two halves. One half is rotated by $m_x \theta_i$ and the other half by $m_y \theta_i$.

This allows the model to capture relative distances in both horizontal and vertical directions independently.

## SVG Diagram: 2D Grid Rotation
<svg width="400" height="200" viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Grid -->
  <rect x="50" y="50" width="100" height="100" fill="none" stroke="black" />
  <line x1="100" y1="50" x2="100" y2="150" stroke="#eee" />
  <line x1="50" y1="100" x2="150" y2="100" stroke="#eee" />
  
  <!-- Indices -->
  <text x="75" y="40">mx</text>
  <text x="30" y="105">my</text>
  
  <!-- Vectors -->
  <rect x="200" y="50" width="150" height="30" fill="#f0f0f0" stroke="black" />
  <text x="210" y="70">[ x_horiz | x_vert ]</text>
  
  <path d="M 230 80 Q 230 120 200 120" fill="none" stroke="blue" marker-end="url(#arrow)" />
  <text x="160" y="140" fill="blue">Rotate by mxθ</text>
  
  <path d="M 320 80 Q 320 120 350 120" fill="none" stroke="red" marker-end="url(#arrow)" />
  <text x="320" y="140" fill="red">Rotate by myθ</text>

  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" />
    </marker>
  </defs>
</svg>

[Back to README](../README.md)
