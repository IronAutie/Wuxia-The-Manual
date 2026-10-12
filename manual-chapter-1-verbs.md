# Chapter 1: Verbs

Every verb in Wuxia, one page each. Pages between first and last are
ordered by codepoint; page numbers recompute as pages are inserted.

| Page | Verb | Glyph |
|------|------|-------|
| 0 | Nil | `∅` U+2205 |
| 1 | Negate | `-` U+002D |
| 2 | Deal | `?` U+003F |
| 3 | Invert | `~` U+007E |
| 4 | Implies | `⇒` U+21D2 |
| 5 | Collate | `±` U+00B1 |
| 6 | Print | `⍠` U+2360 |
| 7 | Stop | `⋄` U+22C4 |
| 8 | Count | `⍳` U+2373 |
| 9 | Nabla | `∇` U+2207 |
| 10 | Cut | `⋮` U+22EE |
| 11 | Anticut | `⋯` U+22EF |
| 12 | Complement | `≀` U+2240 |
| 13 | Diction | `¡` U+00A1 |
| 14 | Decide | `¿` U+00BF |
| 15 | forall | `∀` U+2200 |
| 16 | Forsome | `∃` U+2203 |
| 17 | Plus | `+` U+002B |
| 18 | Star | `*` U+002A |
| 19 | Slash | `/` U+002F |
| 20 | Percent | `%` U+0025 |
| 21 | Quotient | `÷` U+00F7 |
| back | Truth | `⊤` U+22A4 |

Standing rules: unary scalar verbs operate on the back rank of arrays.
Dyadic verbs are prefix. Truth, Nil, and Implies are back-rank scalar
operators. Arithmetic upon Nil yields Nil as result. Scalar back-rank
operators yield Nil when given Nil. Back-rank operations transform the
values of a dictionary, similar to the back rank of an array.
