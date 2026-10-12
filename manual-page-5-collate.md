<p align="right">±</p>
<h1 align="center">Collate</h1>

Collate executes one of three trains upon a value: for less than zero, for zero, or for greater than zero.

Collate works as `± N E G V`: three trains and a value. When V < 0, yield N upon V; when V = 0, yield E upon V; when V > 0, yield G upon V.

The train is selected by the value's sign: negative, zero, or positive.

Bare `± V` — Collate with only a value — is sugar for monadic signum.

`± Z V` replaces V with Z upon V when V is zero.

`± N G V` replaces V with N upon V when V < 0, and with G upon V when V > 0.

When given an array, Collate treats each row of the array as its own train upon V. This transforms arrays.

With a dictionary argument, the keys select the train: `{0: train}` for zero, `{<: train}` for less than zero, `{>: train}` for greater than zero. So `± D V` uses V to decide which train on the dictionary to use on V. If V is an array, then Collate D is applied to the back rank of V.

Examples: TBD.

<p align="right">U+00B1</p>

[👈](manual-page-4-implies.md) [👉](manual-page-6-print.md)
