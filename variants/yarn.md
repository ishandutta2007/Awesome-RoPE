# YaRN (Yet another RoPE for Transformers)

YaRN is an improved method for context window extension that addresses some of the performance loss seen in earlier interpolation techniques.

## Key Improvements
1. **Refined Interpolation**: YaRN divides dimensions into groups. Some are interpolated, some are not, and some are partially interpolated.
2. **Temperature Scaling**: It introduces a scaling factor to the attention mechanism to account for the increased context length, preventing the "entropy collapse" of attention scores.

YaRN allows models like Llama to handle 128k tokens with only a small amount of fine-tuning on long-context data.

## SVG Diagram: YaRN Groups
<svg width="400" height="150" viewBox="0 0 400 150" xmlns="http://www.w3.org/2000/svg">
  <rect x="50" y="40" width="100" height="40" fill="#ffcccc" stroke="black" />
  <text x="60" y="65">Fixed (High freq)</text>
  
  <rect x="150" y="40" width="100" height="40" fill="#ccffcc" stroke="black" />
  <text x="160" y="65">Interpolated</text>
  
  <rect x="250" y="40" width="100" height="40" fill="#ccccff" stroke="black" />
  <text x="260" y="65">Extrapolated</text>
  
  <text x="120" y="110">Different scaling for different groups</text>
</svg>

[Back to README](../README.md)
