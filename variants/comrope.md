# ComRoPE (Commuting RoPE)

ComRoPE is an advanced variant that replaces fixed rotation frequencies with learnable commuting matrices.

## The Concept
In standard RoPE, the rotation angles are fixed and pre-calculated. ComRoPE makes these angles (or rather, the matrices that perform the rotation) learnable.
By using commuting matrices, the model maintains the property that the order of operations doesn't matter, which is essential for preserving the relative distance property of RoPE.

This allow the model to discover the most effective positional encoding scheme for the specific task it is being trained on.

## SVG Diagram: Learnable Matrices
<svg width="400" height="200" viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Matrix representation -->
  <rect x="50" y="50" width="80" height="80" fill="#e0ffe0" stroke="green" />
  <text x="75" y="95" fill="green" font-weight="bold">M</text>
  
  <text x="150" y="95">×</text>
  
  <rect x="180" y="50" width="80" height="80" fill="#f0f0f0" stroke="black" />
  <text x="210" y="95">x</text>
  
  <text x="50" y="150" fill="green">Learnable Commuting Matrix</text>
</svg>

[Back to README](../README.md)
