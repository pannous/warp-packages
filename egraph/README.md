# egraph

Equality saturation over warp code (an e-graph, as in [egg](https://egraphs-good.github.io/)): laws and rules add
every form they make equal to the code, losing none, and the smallest form is taken out. Unlike a rule set
`rules {…}`, which rewrites one way in order, an e-graph can hold a law like `a * b = b * a`.

```warp
use egraph
algebra = law(data(a * b), data(b * a)) + rule(data(a * 1), data(a)) + rule(data(a * b + a * c), data(a * (b + c)))
print simplify(data(x * y + y * z), algebra)                 # y*(x+z)
print equal(data(p * (q * r)), data((r * q) * p), algebra)   # yes
```

- `rule(from, to)`: code shaped `from` becomes `to`, one way; `law(a, b)`: both ways (a way whose result names a
  variable the other side lacks is left out). In a pattern every name in an operand's place is a variable; a call's
  head and numbers stand for themselves.
- `simplify(code, rules)`: the smallest equal code (fewest parts). `equal(a, b, rules)`: whether the rules prove them equal.
- Limits: `node_limit` (10000 e-nodes) and `round_limit` (30 rounds). Laws that never saturate (associativity with
  commutativity grows without end) stop there with a warning; the form found is then the smallest so far.
- Not yet: guards (`a / a = 1` only for a ≠ 0) and constant folding (e-class analyses), costs other than size.

Tests: `warp test` in this folder. Try it: `warp example.warp`. Background: notes/egraphs.md in warp.
