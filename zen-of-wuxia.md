# The Zen Of Wuxia (2026-10-10)

Guiding principles of the Wuxia APL dialect, in the manner of the Zen
of Python. Each line earned, none invented.

1. Failures should be quiet.
2. Unless, you are a dingbat.
3. Anticuts never ship. Cuts do.
4. Inheritance is for the Dutch.
5. We have our own ways to mix in.
6. Loose scripts sink ships.
7. Wuxia is magical. Data is not.

## Explanation

1. The language swallows failures into Nil — the caller gets quiet,
   not noise.
2. A dingbat is anyone second-guessing how Wuxia is supposed to work:
   the classic micromanager. Failures stay quiet for those who trust
   the mechanism; the dingbat who needs to watch it happen gets the
   noise they asked for.
3. ⋯ throws to the debugger, so it never ships; ⋮ logs and goes quiet,
   so it does. The sandbox gets the anticut, the product gets the cut.
4. The MRO maze belongs to Guido's language. Python's inheritance is
   the Dutch problem; we don't have it.
5. Our own ways to mix in: primary at class level — ⊑, what it is;
   secondary at method level — ⋐, what it can do; tertiary at property
   level — ⊩, what it has.
6. Sloppy scripting sinks products. Wuxia is tight: complete mixins,
   read-only α, fixed tiers.
7. And the results speak: industrial-quality rapid development — the
   willingness to spend the effort to achieve change with magical
   results. Data, though, is not magical: named before use, no magic
   numbers.
