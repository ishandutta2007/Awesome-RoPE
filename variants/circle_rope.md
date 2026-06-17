# Circle-RoPE

Circle-RoPE is a specialized version of RoPE designed for Large Vision-Language Models (LVLMs).

## The Concept
Standard 2D RoPE can struggle when the aspect ratio or resolution of images changes significantly between training and inference. Circle-RoPE decouples the rotary embeddings to make them more robust to these changes.

It ensures that the positional signal remains consistent even when the image is resized or cropped, which is crucial for multimodal models that process a wide variety of visual inputs.

## SVG Diagram: Decoupled Rotation
<svg width="400" height="200" viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Circular layout -->
  <circle cx="100" cy="100" r="60" fill="none" stroke="black" stroke-dasharray="4,4" />
  <circle cx="100" cy="100" r="40" fill="none" stroke="blue" />
  
  <rect x="70" y="70" width="60" height="60" fill="none" stroke="red" stroke-width="2" />
  
  <text x="200" y="90">Decoupled from fixed grids</text>
  <text x="200" y="110">Robust to aspect ratio shifts</text>
</svg>

[Back to README](../README.md)
