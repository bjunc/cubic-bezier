# Getting Started

CubicBezier aims to replicate the CubicBezier timing function found
in CSS used with the animation-timing-function property and the 
transition-timing-function property. 

A Cubic Bezier curve is defined by four points `P0`, `P1`, `P2`, and `P3`.
`P0` and `P3` are the start and the end of the curve and, in CSS these 
points are fixed as the coordinates are ratios. `P0` is (`0`, `0`) and 
represents the initial time and the initial state, `P3` is (`1`, `1`) 
and represents the final time and the final state.

Since `x` is always between `0` and `1`, and `y` is almost always also
between `0` and `1`, it is useful to treat them as percentages. 
Where `x` is the percentage of time that has elapsed in your 
animation / transition, and `y` is the percentage your object(s)
should have moved between their start and end positions. 


## Syntax

You can use atoms to represent common control points, or pass a control 
point tuple. The examples below are equivelant:

```elixir
CubicBezier.solve(0.25, :ease_out_quad)
CubicBezier.solve(0.25, {0.250,  0.460,  0.450,  0.940})
```

This will return a `y` position of ~`0.45`, given an `x` of `0.25`. 

> Ease-Out-Quad is fast at first, and slow towards the end.