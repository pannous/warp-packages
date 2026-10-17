# warp-packages

The default package registry of the [warp](https://github.com/pannous/warp) language: every package here is found just
by its name, no URL, no install step.

```warp
use colors
print to_hex(complement(from_hex("#ff8800")))   # #0077ff
```

warp fetches the package the first time a program uses it and keeps it in `~/.cache/warp/packages`.

## Packages

| package | what it does |
|---|---|
| [colors](colors) | hex and hsl conversions, mixing, palettes and contrast for draw's colors |
| [geometry](geometry) | 2D vectors, polygons, areas, point-in-polygon |
| [webgl](webgl) | polylines, filled polygons, stars, grids, function plots and bar charts on warp's canvas |
| [ciphers](ciphers) | Caesar, ROT13, Atbash, Vigenère and Morse code |
| [life](life) | Conway's Game of Life, as text or on the canvas |
| [svg](svg) | SVG pictures and bar charts as text; a package of several files that passes on chosen words |
| [uniscript](uniscript) | readable ASCII names for Unicode (`\:alpha` is α), from [pannous/uniscript](https://github.com/pannous/uniscript) |

## Using a package

`use <name>` in a program, or on the command line: `warp 'use colors; to_hex(red)'`.
Without a version a program gets the package as it is on `main`. To pin a version:

```warp
use colors version 1.0.0     # exactly this release
use colors >= 1.0            # this one or later
```

or for a whole project in its `packages.warp`:

```warp
colors: 1.0.0
geometry: latest
```

A version is the git tag `<name>@<version>` of this repository (`colors@1.0.0`). A file of the same name beside the
program (`colors.warp`) or in warp's own library wins over the package.

## Adding a package

1. A folder named like the package, holding `<name>.warp`: the module that `use <name>` loads. Declare its version at
   the top with `version 1.0.0`. More files may lie beside it: what the main file `use`s reaches the programs too,
   a `from shapes import rect, circle` only the words it names, so the main file is the package's export list
   (see [svg](svg)).
2. `package.warp`, a short manifest: `description: "…"` and `license: MIT`.
3. `README.md` with one usage example, and `example.warp`: a program that shows the package at work and checks
   itself with `assert`, run with `warp example.warp` in the folder.
4. A commit on `main` and the tag of its first release: `git tag <name>@1.0.0 && git push origin main <name>@1.0.0`.

A package that lives in a repository of its own gets a proxy folder instead: `package.warp` names it
(`repository: owner/repo`, `version: 1.2.3` for its tag `v1.2.3`, and `library: "path/to/lib"` for a prebuilt
WebAssembly library, which the folder's `<name>.warp` binds); see [uniscript](uniscript).

All code here is our own and MIT licensed ([LICENSE](LICENSE)): programs may use it freely.
