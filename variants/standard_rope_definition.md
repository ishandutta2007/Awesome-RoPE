# Standard RoPE: Definition

Rotary Position Embedding (RoPE) is a method for encoding positional information in transformer models. Introduced by Su et al. in the RoFormer paper (2021), it represents a paradigm shift from additive positional embeddings to a multiplicative rotation-based approach.

## Key Concept
RoPE encodes the absolute position of a token by applying a rotation matrix to the token's query and key representations. This rotation is performed in a way that the dot product between two tokens' representations depends only on their relative distance, not their absolute positions.

## SVG Diagram: Rotation in 2D Plane
<svg width="200" height="200" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Grid -->
  <line x1="0" y1="100" x2="200" y2="100" stroke="#ccc" stroke-width="1" />
  <line x1="100" y1="0" x2="100" y2="200" stroke="#ccc" stroke-width="1" />
  <!-- Original Vector -->
  <line x1="100" y1="100" x2="170" y2="100" stroke="blue" stroke-width="2" marker-end="url(#arrow)" />
  <text x="175" y="95" fill="blue">x</text>
  <!-- Rotated Vector -->
  <line x1="100" y1="100" x2="150" y2="50" stroke="red" stroke-width="2" marker-end="url(#arrow)" />
  <text x="155" y="45" fill="red">x'</text>
  <!-- Angle -->
  <path d="M 140 100 A 40 40 0 0 0 130 70" fill="none" stroke="green" stroke-width="2" />
  <text x="135" y="85" fill="green">θ</text>
  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" />
    </marker>
  </defs>
</svg>

[Back to README](../README.md)
