# Simple Transforms

## Rotation
Rotation transforms an image or signal by turning it around a foxed point, usually the center. This is a geometric transformation that involves a matrix operation to map input coordinates to new rotated coordinates.

For a point $(x, y)$ in 2D space, rotation by an angle θ around the origin is given by:
\[
\begin{bmatrix}
x' \\
y'
\end{bmatrix}
=
\begin{bmatrix}
\cos \theta & -\sin \theta \\
\sin \theta & \cos \theta
\end{bmatrix}
\begin{bmatrix}
x \\
y
\end{bmatrix}
\]
