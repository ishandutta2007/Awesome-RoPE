# Standard RoPE: Mechanism

The mechanism of RoPE involves splitting the $d$-dimensional embedding vector into $d/2$ pairs of components. Each pair is treated as a point in a 2D plane and rotated.

## How it works
For a vector $\mathbf{x} = [x_1, x_2, ..., x_d]^T$, we pair the elements as $(x_1, x_2), (x_3, x_4), ..., (x_{d-1}, x_d)$.
Each pair $(x_{2i-1}, x_{2i})$ is then rotated by an angle $m\theta_i$, where $m$ is the position of the token and $\theta_i$ is a pre-defined frequency.

The rotation for a pair $(x_1, x_2)$ at position $m$ is:
$$ \begin{pmatrix} x'_1 \\ x'_2 \end{pmatrix} = \begin{pmatrix} \cos m\theta_1 & -\sin m\theta_1 \\ \sin m\theta_1 & \cos m\theta_1 \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \end{pmatrix} $$

## SVG Diagram: Chunked Rotation
<svg width="400" height="150" viewBox="0 0 400 150" xmlns="http://www.w3.org/2000/svg">
  <!-- Vector Boxes -->
  <rect x="20" y="40" width="60" height="30" fill="#f0f0f0" stroke="black" />
  <text x="35" y="60">x1, x2</text>
  <rect x="100" y="40" width="60" height="30" fill="#f0f0f0" stroke="black" />
  <text x="115" y="60">x3, x4</text>
  <text x="175" y="60">...</text>
  
  <!-- Rotation Labels -->
  <path d="M 50 70 Q 50 110 80 110" fill="none" stroke="black" marker-end="url(#arrow)" />
  <text x="85" y="115">Rotate by mθ₁</text>
  
  <path d="M 130 70 Q 130 110 160 110" fill="none" stroke="black" marker-end="url(#arrow)" />
  <text x="165" y="115">Rotate by mθ₂</text>

  <defs>
    <marker id="arrow" viewBox="0 0 10 10" refX="5" refY="5" markerWidth="6" markerHeight="6" orient="auto-start-reverse">
      <path d="M 0 0 L 10 5 L 0 10 z" />
    </marker>
  </defs>
</svg>

[Back to README](../README.md)
