# Wuxia — Book Structure (2026-10-20)

Book: "Wuxia: Programming as Stagecraft"
Hardcover, 6" x 9". Black, copper tracing, silk bookmark.

## Cover

- Front, center: the Hero ideograph (U+4FA0), with "Wuxia" in
  English script underneath it.
- Front, three-quarters down: the byline "Kung Fu for the
  Programmer".
- Front, bottom: "Andrew Jonathan Fine, MSCS Villanova 1982".
- Spine: the ideograph, "Wuxia", the author's name, and six
  diagonal stripes: sixth-degree black belt, as the founder.
- Back cover: The Zen of Wuxia, seven lines.
- Back inside cover: the line-by-line explanation of the Zen.

## Chapters

- Chapter 1: Style. All the language glyphs, in sections by
  purpose. A front table of contents stands before the first
  section. Sections:
  1. Truth and Nil
  2. Arithmetic
  3. Constants and Chance
  4. Number Theory
  5. Polynomials and Roots
  6. Matrices
  7. Arrays
  8. Boxes
  9. Sets and Membership
  10. Trains
  11. Functions
  12. Errors
  13. Classes and Properties
  14. The Virtual
  Within each section: create the pages, quarter each page, and
  sort the quarters by Unicode.
  Subsections by arity within each section: niladic, monadic,
  dyadic. A glyph repeats in every subsection its arities reach,
  and an ambivalent glyph binds a different English name in each:
  its monadic name among the monadics, its dyadic name among the
  dyadics. Every subsection has its own blank title page, with
  its name at top center.
- Final chapter: Dungeon. The dungeon glyphs (dungeon-glyphs.md):
  Places, Classes, Objects, Entities, Food, Species inheritance.
  Filled 2026-10-20, similar to Style: a title page per section,
  quartered pages, meanings in the centers, overflows on their own
  pages. The Species declarations stand as quarters of their own:
  the Inherits glyph, the species as binding, the declaration in
  the center. A species has no glyph of its own yet, so its
  quarter carries U+2047, the double question mark: in this book
  that glyph means a todo, a glyph not yet assigned. A species
  takes its own glyph from the book's tables first, then from the
  display.c codepoint table in the NetHack tree. After that pass,
  15 quarters remain todos: VampireLady, VampireLord, Nosferatu,
  BabyDragon, Dragon, the four Merfolk, GrandMaster, and the
  IntegerBounded properties (max, min, epsilon, nabla). The book is
  one volume: Key, Contents, Style,
  Dungeon, and the two indexes at the very back covering both
  chapters.
- A DIY chapter: the holographic display (repo: Wuxia-Display).

## Front matter

- First page of the book: the Key, listing all chapters,
  sections, and indices by page number. The Contents follows.

## Page layout

- In each chapter, every page is split both horizontally and
  vertically: four quarters to a page, each quarter devoted to
  one glyph. Four glyphs to a page.
- The Style chapter is organized into sections by purpose;
  blank pages divide the sections, set between the quartered
  pages.
- Quarter order on a page: 1 top left, 2 top right, 3 bottom
  left, 4 bottom right.
- The Wuxia quarter (U+4FA0, binding Wuxia, meaning "The Hero")
  is always first, on the first page of the Style chapter,
  regardless of any other sorting.
- Within a quarter:
  - top left: the glyph
  - top right: the English binding, right justified
  - bottom left: the Unicode hex
  - center: the meaning, if it is short enough to explain there
  - bottom right: blank; a too-long meaning gets a separate page
    of its own, and that page's number sits just below the
    English binding
- Every page is numbered, bottom center; the vertical divider
  stops short of the number so the two never cross.
- An Index chapter stands after the second section (Arithmetic),
  split in two: English binding to page-by-quarter, then the
  glyph itself to page-by-quarter.
