# life

Conway's Game of Life on a grid that wraps around its edges. A world is a list of rows of 0 (dead) and 1 (alive);
`parse` and `render` read and write it as text, `#` alive and `.` dead.

```warp
use life
world = place(glider, 8, 8, 1, 1)
print render(run(world, 4))                   # the glider, one cell further right and down
```

Words: `parse`, `render`, `empty_world`, `place`, `neighbours`, `step`, `run`, `population`, `draw_world`, and the
patterns `glider`, `blinker`.

Try it: `warp example.warp` (text) or `warp animate.warp` (a glider on the canvas, needs `use draw` beside
`use life`) in this folder.
