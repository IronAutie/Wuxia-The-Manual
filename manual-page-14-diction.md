<p align="right">¡</p>
<h1 align="center">Diction</h1>

At the scalar level, Diction converts a train of length two into a key-value pair.

`¡ A B` yields `{A:B}`. If the train is even, it creates multiple key-value pairs: `¡ A B C D` yields `{A:B,C:D}`. If the train is odd, the value of the final key is Nil: `¡ A B C` yields `{A:B,C:∅}`. If the argument is an array, this is a back vector operator. A train of length one assumes a value of Nil: `¡ A` yields `{A:∅}`. A train of length zero makes both key and value Nil: `¡` yields `{∅:∅}` — nonsense, but it may have a use as a placeholder. Monadic `¡ (a b c)` self-maps into a set.

Examples:

- #0: `¡ A B` ⍠ `{A:B}` ⋄

Further examples: TBD.

<p align="right">U+00A1</p>

[👈](manual-page-13-complement.md) [👉](manual-page-15-decide.md)
