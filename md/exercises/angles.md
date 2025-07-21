# Angles

\begin{tikzpicture}
    \draw (0,0) coordinate (O)
        (-3,0) coordinate (A) -- (O)
        (0,3) coordinate (B) -- (O)
        (2.77,1.15) coordinate (C) -- (O)
        pic [draw, fill=lightgray] {right angle=A--O--B}
        pic ["$3x$", draw, angle radius=0.7cm] {angle=A--O--C}
        pic ["$x$", draw, angle radius=0.6cm] {angle=C--O--B};
\end{tikzpicture}