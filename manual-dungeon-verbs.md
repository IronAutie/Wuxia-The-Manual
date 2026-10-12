# Dungeon Verbs

## Up

▲ U+25B2

Up is the upward/north movement.

`Where⊡up` yields ∅ when `Where⊡Zee` is 0, else Where with Zee decremented. Boundary-checked: the top edge is a quiet Nil, not a negative index.

## Down

▼ U+25BC

Down is the downward/south movement, counterpart to Up.

`Where⊡down` yields ∅ when `Where⊡Zee ≥ Dungeon⊡Zee` (the bottom edge), else `Where⊡Zee + 1`.
