# Context-aware RoPE

Context-aware RoPE is a dynamic variant of RoPE that adjusts its behavior based on the actual content of the tokens.

## The Concept
Unlike standard RoPE, which applies the same rotation to every token regardless of what it is, Context-aware RoPE allows the model to "pay more attention" to certain positions or tokens by modifying the rotation angles dynamically.

The angles become a function of both the position $m$ and the hidden state of the token itself. This allows the model to emphasize semantically important phrases or structures.

## SVG Diagram: Dynamic Rotation
<svg width="400" height="200" viewBox="0 0 400 200" xmlns="http://www.w3.org/2000/svg">
  <!-- Token 1 -->
  <rect x="50" y="50" width="60" height="30" fill="#f0f0f0" stroke="black" />
  <text x="60" y="70">Token A</text>
  <path d="M 80 80 Q 80 120 100 120" fill="none" stroke="blue" marker-end="url(#arrow)" />
  <text x="105" y="125" fill="blue">θ(A)</text>
  
  <!-- Token 2 -->
  <rect x="200" y="50" width="60" height="30" fill="#f0f0f0" stroke="black" />
  <text x="210" y="70">Token B</text>
  <path d="M 230 80 Q 230 150 250 150" fill="none" stroke="red" marker-end="url(#arrow)" />
  <text x="255" y="155" fill="red">θ(B)</text>
  
  <text x="50" y="180">Angles depend on token content</text>

  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" />
    </marker>
  </defs>
</svg>

[Back to README](../README.md)
