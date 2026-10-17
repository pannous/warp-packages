# geometry

2D vectors and the shapes made of them. A `Vec` has `x` and `y`; a polygon is a list of `Vec` corners in order.

```warp
use geometry
a = Vec(3, 4)
print a.magnitude()                           # 5
print a.plus(Vec(1, 1))                       # Vec{x:4 y:5}
hexagon = regular_polygon(Vec(0, 0), 1, 6)
print area(hexagon)                           # 2.598…
print contains(rectangle(Vec(0, 0), 2, 2), Vec(1, 1))  # yes
```

`Vec` methods: `plus`, `minus`, `scaled`, `dot`, `cross`, `magnitude`, `distance`, `normalized`, `rotated`, `angle`.
Words: `lerp`, `circle_area`, `circle_circumference`, `regular_polygon`, `rectangle`, `signed_area`, `area`,
`perimeter`, `centroid`, `bounds`, `contains`.

Try it: `warp example.warp` in this folder.
