# svg

SVG pictures as text, for a web page or a file, and a bar chart in one call.

```warp
use svg
print svg(120, 80, [
	circle(60, 40, 25, from_hex("#ffd700")),
	label(8, 16, "sun & sky", from_hex("#003366"))
])
print bar_chart([3, 5, 2, 8])
```

Words: `svg`, `bar_chart`, `rect`, `circle`, `line`, `polyline`, `polygon`, `label`, and from the colors package
`from_hex`, `mix`, `rainbow`. Colors are draw's numbers `0xAARRGGBB`.

## A package of several files

The package is three files, and only the main one, named like the package, decides what a program gets:

```text
svg/
  svg.warp      the main file: `from shapes import rect, circle, …` and `from colors import from_hex, mix, rainbow`
  shapes.warp   the elements; `from tags import element, coordinate, escape_xml`, `from colors import to_hex`
  tags.warp     XML helpers
```

A package passes its own `use` and `from … import` lines on to the programs that use it (decision
package-reexport), so a `from … import` in the main file is its export list: `use svg` gives `rect` and `rainbow`,
but not shapes' `points_text`, tags' `escape_xml` or colors' `to_hex`, which stay inside the package.

Try it: `warp example.warp` in this folder (it writes svg_example.svg).
