# VRoPE (Video RoPE)

VRoPE is a 3D extension of Rotary Position Embeddings designed for video processing.

## The Concept
Video data consists of spatial dimensions ($x, y$) and a temporal dimension ($t$). VRoPE applies rotations based on all three coordinates.
The embedding vector is divided into three segments, each receiving a rotation corresponding to its respective dimension:
- $m_x \theta_i$ for horizontal position.
- $m_y \theta_i$ for vertical position.
- $m_t \theta_i$ for the frame index (time).

This enables the model to understand the relative position of objects not just within a single frame, but across the entire video sequence.

## SVG Diagram: Spatial-Temporal Rotation
<svg width="400" height="200" viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg">
  <!-- 3D-ish representation -->
  <rect x="50" y="50" width="60" height="60" fill="none" stroke="gray" stroke-dasharray="2,2" />
  <rect x="70" y="70" width="60" height="60" fill="none" stroke="black" />
  <line x1="50" y1="50" x2="70" y2="70" stroke="gray" stroke-dasharray="2,2" />
  <line x1="110" y1="50" x2="130" y2="70" stroke="gray" stroke-dasharray="2,2" />
  
  <text x="60" y="45">x</text>
  <text x="40" y="80">y</text>
  <text x="50" y="140">t (time)</text>
  
  <rect x="200" y="70" width="180" height="30" fill="#f0f0f0" stroke="black" />
  <text x="210" y="90">[ x_h | x_v | x_t ]</text>
  
  <text x="210" y="130">Rotates by (mx, my, mt)</text>
</svg>

[Back to README](../README.md)
