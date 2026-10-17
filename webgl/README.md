# webgl

Charts and shapes on warp's canvas, the one `use draw` paints: in the browser the playground's canvas, natively a
window, or a PNG with `save`. Points are `[x, y]` in pixels, y pointing down.

```warp
use draw
use webgl
canvas(200, 100)
clear(white)
grid(20, 0xFFE0E0E0)
plot(x => sin(x), -pi, pi, blue)
star(50, 50, 40, 16, 5, orange)
show()
```

![example](https://raw.githubusercontent.com/pannous/warp-packages/main/webgl/example.png)

Words: `polyline`, `outline`, `fill_polygon`, `star_points`, `star`, `grid`, `plot`, `bar_chart`, beside draw's
`canvas`, `clear`, `rect`, `circle`, `line`, `label`, `show`, `save`.

`use draw` is needed beside `use webgl` for now: a package's own `use` doesn't reach the program yet.

Try it: `warp example.warp` in this folder (it saves webgl_example.png).
