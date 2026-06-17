# Standard RoPE: Core Benefit

The primary advantage of RoPE over absolute positional embeddings is its ability to naturally represent relative positions through the properties of rotation.

## Relative Distance Preservation
When we compute the attention score (dot product) between a query at position $m$ and a key at position $n$, the result depends only on the relative distance $m - n$.

Mathematically, if $R_\theta^m$ is the rotation matrix for position $m$:
$$ (R_\theta^m \mathbf{q})^T (R_\theta^n \mathbf{k}) = \mathbf{q}^T (R_\theta^m)^T R_\theta^n \mathbf{k} = \mathbf{q}^T R_\theta^{n-m} \mathbf{k} $$

This property allows the model to generalize to sequence lengths it hasn't seen during training, as long as the relative distances remain familiar.

## SVG Diagram: Relative Distance
<svg width="400" height="200" viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Two sectors representing relative rotation -->
  <path d="M 100 100 L 170 100 A 70 70 0 0 0 150 50 Z" fill="#e0e0ff" stroke="blue" />
  <text x="110" y="85" fill="blue">m-n</text>
  
  <text x="200" y="100">Relative angle remains</text>
  <text x="200" y="120">constant for same m-n</text>

  <!-- Circles -->
  <circle cx="100" cy="100" r="70" fill="none" stroke="#eee" />
</svg>

[Back to README](../README.md)
