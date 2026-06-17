# Linear Interpolation RoPE (PI)

Position Interpolation (PI) is one of the simplest methods for extending the context window of a pre-trained model.

## The Concept
If a model was trained on a context length $L$, and we want it to work on length $L' > L$, we can "squeeze" the $L'$ positions into the $0 \dots L$ range.
Instead of using the integer position $m$, we use $m' = m \cdot (L / L')$.

By doing this, the rotational angles encountered by the model during inference remain within the range of angles it saw during training.

## SVG Diagram: Index Compression
<svg width="400" height="150" viewBox="0 0 400 150" xmlns="http://www.w3.org/2000/svg">
  <!-- Original scale -->
  <line x1="50" y1="50" x2="350" y2="50" stroke="black" stroke-width="2" />
  <circle cx="50" cy="50" r="3" fill="blue" />
  <circle cx="150" cy="50" r="3" fill="blue" />
  <circle cx="250" cy="50" r="3" fill="blue" />
  <circle cx="350" cy="50" r="3" fill="blue" />
  <text x="50" y="40">0</text>
  <text x="340" y="40">L</text>
  
  <!-- Interpolated scale -->
  <line x1="50" y1="100" x2="350" y2="100" stroke="red" stroke-width="2" />
  <circle cx="50" cy="100" r="3" fill="red" />
  <circle cx="100" cy="100" r="3" fill="red" />
  <circle cx="150" cy="100" r="3" fill="red" />
  <circle cx="200" cy="100" r="3" fill="red" />
  <circle cx="250" cy="100" r="3" fill="red" />
  <circle cx="300" cy="100" r="3" fill="red" />
  <circle cx="350" cy="100" r="3" fill="red" />
  <text x="50" y="125">0</text>
  <text x="340" y="125">L'</text>
  
  <text x="180" y="145" fill="red">More tokens, same range of angles</text>
</svg>

[Back to README](../README.md)
