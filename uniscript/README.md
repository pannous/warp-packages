# uniscript

Readable ASCII names for Unicode: `\:alpha` is α, `<:upper A>` is ᴬ. The package lives in its own repository,
[pannous/uniscript](https://github.com/pannous/uniscript); this folder only points to it (`package.warp`) and holds
warp's binding to its prebuilt C library (`uniscript.warp`).

```warp
use uniscript
print uniscript("\\:alpha + \\:beta")   // α + β
```

Another version than the one in `package.warp`: `uniscript: 1.0.11` in your `packages.warp`.
