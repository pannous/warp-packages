# colors

Conversions and palettes for warp's colors, the numbers `0xAARRGGBB` that `use draw` paints with (`rgb`, `hsv`,
`red`, …): a palette color fills a `rect` as it is.

```warp
use colors
orange = from_hex("#ff8800")
print [to_hex(c) for c in triad(orange)]      # ["#ff8800" "#00ff88" "#8800ff"]
print to_hex(mix(orange, white, 0.5))         # lighter: lighten(orange, 0.5) is the same
print contrast(black, white)                  # 21, the WCAG contrast ratio
```

Words: `from_hex`, `to_hex`, `hsl`, `to_hsl`, `red_of`, `green_of`, `blue_of`, `mix`, `lighten`, `darken`, `gradient`,
`rotate_hue`, `complement`, `triad`, `analogous`, `rainbow`, `luminance`, `contrast`, `text_color_on`.

Try it: `warp example.warp` in this folder.
