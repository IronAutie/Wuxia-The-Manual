# Wuxia, The Manual — outline (2026-10-11, current through the AntiSignum burst)

Public repo: IronAutie/Wuxia-The-Manual. Three chapters: Verbs, Nouns, Zens.

## Chapter 1: Style (one page per verb)

Ordering: pages between first and last ordered by codepoint index;
page numbers recompute as pages are inserted. First: Nil (page 0).
Last: Truth (back page).

Layout (2026-10-20): in each chapter, every page is split both
horizontally and vertically — four quarters to a page, and each
quarter is devoted to one glyph. Four glyphs to a page.

Organization (2026-10-20): the Style chapter is organized into
sections by purpose. Blank pages divide the sections, set between
the quartered pages. A front table of contents stands before the
first section. Sections: Truth and Nil; Arithmetic; Constants and
Chance; Number Theory; Polynomials and Roots; Matrices; Arrays;
Boxes; Sets and Membership; Trains; Functions; Errors; Classes
and Properties; The Virtual. Within each section: create the
pages, quarter each page, and sort the quarters by Unicode.
Subsections (2026-10-20): within each section, glyphs are
subsectioned by arity: niladic, monadic, dyadic. A glyph repeats
in every subsection its arities reach. An ambivalent glyph has a
different English binding per arity: the monadic subsection
binds its monadic name, the dyadic subsection its dyadic name.
Every subsection has its own blank title page, with its name at
top center. Meanings in the quarters are arity-sliced (agreed
2026-10-20, built the same night): each quarter prints only its own
arity's segment of the recorded meaning, so nothing prints twice;
the general lead-in stays; unsegmented ambivalent entries print
whole in both subsections.

Quarter order on a page: 1 top left, 2 top right, 3 bottom left,
4 bottom right.

First quarter of the book: the Wuxia quarter (the glyph U+4FA0,
binding Wuxia, meaning "The Hero") is always first, on the first
page of the Style chapter, regardless of any other sorting.

Within a quarter:
- top left: the glyph
- top right: the English binding, right justified
- bottom left: the Unicode hex
- center: the meaning, if it is short enough to explain there
- bottom right: blank
- if the meaning is too long for the quarter, it gets a separate
  page of its own, and that page's number is carried just below
  the English binding (moved there 2026-10-20; it began in the
  bottom right)
Front matter (2026-10-20): the first page of the book is the
Key: a page labelled Key listing all chapters, sections, and
indices by page number. The Contents follows it.
In the PDF, the page numbers are buttons: the numbers in the
Key, the Contents, and both indexes jump to their page (index
references land on the exact quarter), and the overflow numbers
under the bindings jump to their overflow pages.
Book mechanics (2026-10-20): every page is numbered, bottom
center; the vertical divider stops short of the number so the
two never cross. An Index chapter stands after the second
section (Arithmetic), split in two: first the English binding to
page-by-quarter (page-quarter, e.g. 18-2), then the glyph itself
to page-by-quarter.

(Supersedes the earlier layout: symbol top right, spelling top
center, codepoint bottom right.)

First paragraph: one-sentence summary, ideally. Then elaboration, then examples.

### Pages in place

| Page | Verb | Glyph | Summary | Elaboration | Examples | Public repo |
| 0 | Nil | `∅` U+2205 | yes | yes | yes (quad-colon set) | yes |
| 1 | Negate | `-` U+002D | pending | unary minus, scalar and array | TBD | yes |
| 2 | Deal | `?` U+003F | pending | scalar as expected; array fills entire back rank with limited values | TBD | yes |
| 3 | Invert | `~` U+007E | pending | monadic only; scalar as expected (`~ 0` is `1`); back rank scalar unary | draft (mirror Nil's 0/1) | yes |
| 4 | Implies | `⇒` U+21D2 | yes | TBD | implication truth table | yes |
| 5 | Signum | `∓` U+2213 | pending | just like math signum; back rank scalar unary | `#0: ∓ 5 ⍠ 1 ⋄`, `#1: ∓ 0 ⍠ 0 ⋄`, `#2: ∓ ¯3 ⍠ ¯1 ⋄` | yes |
| 6 | AntiSignum | `⊰` U+22B0 | pending | applies one of three trains upon a value, selected by the value's sign | TBD | no (local only, 2026-10-11) |
| 7 | Print | `⍠` U+2360 | yes ("print value from right, pass to left") | pending | pending | outline only, no page file yet |
| 8 | Stop | `⋄` U+22C4 | yes | yes (terminates train mid-statement; aids storage of train while execution begins on right hand side) | TBD | yes |
| back | Truth | `⊤` U+22A4 | yes | yes | yes (quad-colon set) | yes |

Standing rules on all unary scalar verbs (2026-10-11): operate on the
back rank of arrays; Truth, Nil, Implies are back rank scalar operators.
Dyadics are prefix: verb first, then arguments; whichever side holds
the array, the back rank rule holds.

### Defined verbs not yet in the manual

- `¿` Decide: switch on n×2k train tables, first-match wins, default C is filler, unmatched→Nil, no error.
- `¡` Diction: dict/table builder, wraps `__dict__`; `¡ A B` = `{A:B}`, monadic `¡ (a b c)` = set.
- `≡` Congruent
- `⍳` Count: magical iota; given a shape fills an array matching that shape; `⍳ 2 3` holds two rows of `0 1 2, 0 1 2` (index origin 0); scalar argument behaves classically.
- `∀` forall, `∃` Forsome, `∄` Fornone (U+2204, defined as `~Forsome`)
- `⋮` Cut (U+22EE), `⋯` Anticut (U+22EF)
- Error verbs: Errmsg `❎` U+274E, Errline `❌` U+274C, Errdmd `✧` U+2727, Debugger `✔` U+2714

Deferred by him: `⎕` APL quad (U+2395), not added yet.

## Chapters 2 and 3

Chapter 2 (Nouns): dungeon objects, food, classes. The dungeon glyphs moved into their own chapter file, `dungeon-glyphs.md` — the final chapter, titled Dungeon, 2026-10-20 (94 dictionary rows plus the Species inheritance section, verbatim).
Chapter 3 (Zens): not started.
