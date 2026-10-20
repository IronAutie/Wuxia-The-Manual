# Dungeon — the final chapter of the Manual (2026-10-20)

The glyphs of the dungeon itself: its places, its classes, its
objects, its entities, its food, and its species. Moved here from the
glyph dictionary at his order: the dungeon glyphs get their own chapter,
the final chapter of the book, titled Dungeon.
Rows are verbatim from the dictionary.

## Places

| Name     | Glyph | Codepoint | Meaning |
|----------|-------|-----------|---------|
| Screen   | §     | U+00A7    | The Screen — intrinsic 20×60 array (16 play + 4 I/O rows) |
| Dungeon  | £     | U+00A3    | The Dungeon — literally the set of all levels |
| Level    | ¶     | U+00B6    | Level — the pilcrow: a single dungeon level, member of £ Dungeon |
| Where    | @     | U+0040    | Where the hero is — bound to '@', the roguelike player glyph. `Where⊡Zee` yields `Where [-1` (last); `Where⊡Wye` yields `Where [1` (midposition — middle of 3 coords); `Where⊡Exx` yields `Where [0` (zero). INDICES START AT ZERO |
| Up       | ▲     | U+25B2    | Up — the upward/north movement. `Where⊡up` yields ∅ when `Where⊡Zee` is 0, else Where with Zee decremented (refined 2026-10-10: boundary-checked — top edge is a quiet Nil, not a negative index) |
| Down     | ▼     | U+25BC    | Down — the downward/south movement, counterpart to Up. `Where⊡down` yields ∅ when `Where⊡Zee ≥ Dungeon⊡Zee` (bottom edge), else `Where⊡Zee + 1` (confirmed 2026-10-10) |
| Cell     | ¢     | U+00A2    | A dungeon cell — the cent sign joins the family: § £ ¢. `Cell⊡location ← £ Where`: the cell's location is the Dungeon at Where. A dungeon square IS a dictionary of instances (the Ⓘ registry's entries present at that square) |

## Classes

| Name     | Glyph | Codepoint | Meaning |
|----------|-------|-----------|---------|
| Class    | ⊙     | U+2299    | Class — the circled dot. `X⊡Class` gets a RANK-2 ARRAY OF TRAINS: a class IS a decision table made of trains. Class instances are callable; the train defaults to Nil (∅) |
| Classes  | Ⓒ     | U+24B8    | Classes — the set of all classes (plural of Class), parallel to £ Dungeon as the set of all levels. Implementation: a single twin (bidirectional word↔glyph) dictionary at global scope |
| Instances | Ⓘ    | U+24BE    | Instances — the TABLE/set of all instances (plural), parallel to Ⓒ Classes. Implementation: a single twin (bidirectional word↔glyph) dictionary at global scope. Instance identity is the (glyph, hash-at-creation) tuple, used as the key field in both the global instance dictionary and each square (Cell) dictionary |
| Instance | 𝕀     | U+1D540   | Instance — the INDIVIDUAL instance (singular), distinct from Ⓘ the table. Joins the blackboard family (𝕏 𝕐 ℤ ℙ 𝕆). Carries the (glyph, hash-at-creation) identity tuple |
| Inherits | ⊑     | U+2291    | Inherits — the inheritance operator (square subset of) |
| Object   | 𝕆     | U+1D546   | Object — a DUNGEON object, not a generic OOP object. The blackboard O joins the projection family (𝕏 𝕐 ℤ ℙ): the root of the dungeon's object hierarchy, what every dungeon entity inherits from |
| Isa      | ⋿     | U+22FF    | Isa — the is-a / instantiation operator (2026-10-10). Monadic `⋿ Y`: Y is a class to copy data from; new instance.ε = Y.ε. Dyadic `⋿ Y X`: X is a class, optional initializer; new instance.ε = X.ε (new 2026-10-14) |

## Objects

| Name     | Glyph | Codepoint | Meaning |
|----------|-------|-----------|---------|
| Armor    | 𝔸     | U+1D538   | Armor — the blackboard A: a dungeon object (armor), first of the dungeon entity glyphs |
| Weapon   | 𝕎     | U+1D54E   | Weapon — the blackboard W: a dungeon object (weapon), second of the dungeon entity glyphs |
| Ring     | ℝ     | U+211D    | Ring — the blackboard R: a dungeon object (ring), third of the dungeon entity glyphs |
| Wand     | ⊣     | U+22A3    | Wand — left tack: a dungeon object (wand) |
| Scroll   | 𝕊     | U+1D54A   | Scroll — the blackboard S: a dungeon object (scroll) |
| Tool     | 𝕋     | U+1D54B   | Tool — the blackboard T: a dungeon object (tool) |
| Food     | 𝔽     | U+1D53D   | Food — the blackboard F: a dungeon object (food) |
| Amulet   | ❁     | U+2741    | Amulet — eight-petalled floret: a dungeon object (amulet). (Was U+1DF76, tofu on device — swapped 2026-10-10) |
| Gem      | ●     | U+25CF    | Gem — solid black circle: a dungeon object (gem). (Was U+2733 — swapped 2026-10-10) |
| Potion   | ❗    | U+2757    | Potion — heavy exclamation: a dungeon object (potion) |

## Entities

| Name     | Glyph | Codepoint | Meaning |
|----------|-------|-----------|---------|
| Monster  | 𝕄     | U+1D544   | Monster — the blackboard M: a dungeon monster, first of the monster glyphs |
| Player   | ☻     | U+263B    | Player — black smiling face: the dungeon's player entity. Inherits Monster plus a few extra fields Monster does not have |

## Food

| Name     | Glyph | Codepoint | Meaning |
|----------|-------|-----------|---------|
| Tin      | ✪     | U+272A    | Tin — circled white star: a dungeon food item (tin), first of the object species |
| RefriedBeans | ❻  | U+277B    | RefriedBeans — dark-encircled six: grants teleportation |
| Spinach   | ❼     | U+277C    | Spinach — dark-encircled seven: Popeye strength |
| Sushi     | ㊗    | U+3297    | Sushi — circled congratulation: the sushi/sashimi food category. (Was U+2722 — swapped 2026-10-11) |
| CarpSashimi   | ㊀     | U+3280   | CarpSashimi — circled kanji: sushi item |
| WhaleSashimi  | ㊁     | U+3281   | WhaleSashimi — circled kanji: sushi item |
| EelSashimi    | ㊂     | U+3282   | EelSashimi — circled kanji: sushi item |
| SalmonSashimi | ㊃     | U+3283   | SalmonSashimi — circled kanji: sushi item |
| TunaSashimi   | ㊄     | U+3284   | TunaSashimi — circled kanji: sushi item |
| CrabSashimi   | ㊅     | U+3285   | CrabSashimi — circled kanji: sushi item |
| DragonSashimi | ㊆     | U+3286   | DragonSashimi — circled kanji: sushi item |
| TurtleSashimi | ㊇     | U+3287   | TurtleSashimi — circled kanji: sushi item |
| Oyster        | ㊈     | U+3288   | Oyster — circled kanji: sushi item |
| Uni           | ㊉     | U+3289   | Uni — circled kanji: sushi item |
| Gyuniku       | ㊊     | U+328A   | Gyuniku — circled kanji: sushi item |
| Asian     | 🈐    | U+1F210   | Asian — squared hand: the Asian food category. (Was U+328C — swapped 2026-10-11) |
| Ramen         | 🈑     | U+1F211   | Ramen — squared cjk unified ideograph-5b57: Asian food |
| FortuneCookie | 🈒     | U+1F212   | FortuneCookie — squared cjk unified ideograph-53cc: Asian food |
| Kelp          | 🈓     | U+1F213   | Kelp — squared katakana de: Asian food |
| Dumplings     | 🈔     | U+1F214   | Dumplings — squared cjk unified ideograph-4e8c: Asian food |
| BowlOfRice    | 🈕     | U+1F215   | BowlOfRice — squared cjk unified ideograph-591a: Asian food |
| SpringRolls   | 🈖     | U+1F216   | SpringRolls — squared cjk unified ideograph-89e3: Asian food |
| Tofu          | 🈗     | U+1F217   | Tofu — squared cjk unified ideograph-5929: Asian food |
| PreservedEgg  | 🈘     | U+1F218   | PreservedEgg — squared cjk unified ideograph-4ea4: Asian food |
| CantoneseDuck | 🈙     | U+1F219   | CantoneseDuck — squared cjk unified ideograph-6620: Asian food |
| Deli      | ❖     | U+2756    | Deli — black diamond minus white X: the delicatessen food category (the 25 staples, names lost 2026-10-10 — rebuild pending) |
| Fruit     | 🀰    | U+1F030   | Fruit — domino tile back: the fruit food category |
| Soup      | ⑳     | U+2473    | Soup — circled twenty: the soup category |
| Candy     | 🀪    | U+1F02A   | Candy — mahjong joker: the candy category |
| Meat      | 丽     | U+4E3D    | Meat — CJK beautiful: the meat category |
| Egg       | ø     | U+00F8    | Egg — o with stroke: the egg. (Was U+2800 — swapped 2026-10-11) |
| Creature  | ꝋ     | U+A74B    | Creature — o with long stroke overlay: the monster-shuffle category |
| Goodbar   | 🀀     | U+1F000    | Goodbar — mahjong east wind: candy |
| Honee     | 🀁     | U+1F001    | Honee — mahjong south wind: candy |
| DRation   | 🀂     | U+1F002    | DRation — mahjong west wind: candy |
| DoveBar   | 🀃     | U+1F003    | DoveBar — mahjong north wind: candy |
| CrowBar   | 🀩     | U+1F029    | CrowBar — mahjong winter: candy |
| AcidBroth         | ❶     | U+2776    | AcidBroth — dark-encircled number: soup |
| GoldenSoup        | ❷     | U+2777    | GoldenSoup — dark-encircled number: soup |
| StonedSoup        | ❸     | U+2778    | StonedSoup — dark-encircled number: soup |
| MoldySoup         | ❹     | U+2779    | MoldySoup — dark-encircled number: soup |
| Manwich           | ❺     | U+277A    | Manwich — dark-encircled number: soup |
| CreamOfAlgaeSoup  | ❾     | U+277E    | CreamOfAlgaeSoup — dark-encircled number: soup |
| ChickenNoodleSoup | ❿     | U+277F    | ChickenNoodleSoup — dark-encircled number: soup |
| Apple     | 🀲     | U+1F032    | Apple — domino tile: fruit, inherits Fruit |
| Orange    | 🀳     | U+1F033    | Orange — domino tile: fruit, inherits Fruit |
| Pear      | 🀴     | U+1F034    | Pear — domino tile: fruit, inherits Fruit |
| Melon     | 🀵     | U+1F035    | Melon — domino tile: fruit, inherits Fruit |
| Banana    | 🀶     | U+1F036    | Banana — domino tile: fruit, inherits Fruit |
| Carrot    | 🀷     | U+1F037    | Carrot — domino tile: fruit, inherits Fruit |
| Fig       | 🀸     | U+1F038    | Fig — domino tile: fruit, inherits Fruit |
| Lemon     | 🀹     | U+1F039    | Lemon — domino tile: fruit, inherits Fruit |
| Lime      | 🀺     | U+1F03A    | Lime — domino tile: fruit, inherits Fruit |
| Grapes    | 🀻     | U+1F03B    | Grapes — domino tile: fruit, inherits Fruit |
| Sundry    | ㉧     | U+3267    | Sundry — circled ideograph: the sundry/miscellaneous category |
| Tomb      | ㉈     | U+3248    | Tomb — circled 10 on black square: safe-row tin, now Sundry |
| Pesto     | ㉉     | U+3249    | Pesto — circled 20 on black square: safe-row tin, now Sundry |
| KelpFrond | ㊌     | U+328C    | KelpFrond — circled water: sundry item (kelp is seaweed) |
| EucalyptusLeaf | ㊍ | U+328D    | EucalyptusLeaf — circled wood: sundry item |
| CandyBar  | ㊎     | U+328E    | CandyBar — circled metal: sundry item |
| LembasWafer | ㊏   | U+328F    | LembasWafer — circled earth: sundry item |
| CramRation | ㊐    | U+3290    | CramRation — circled sun: sundry item |
| FoodRation | ㊩    | U+32A9    | FoodRation — circled medicine: sundry item |
| KRation   | ㊪     | U+32AA    | KRation — circled religion: sundry item |
| CRation   | ㊫     | U+32AB    | CRation — circled study: sundry item |
| CloveOfGarlic | ㊟ | U+329F    | CloveOfGarlic — circled attention: sundry item |
| SprigOfWolfsbane | ㊠ | U+32A0 | SprigOfWolfsbane — circled item: sundry item |
| LumpOfRoyalJelly | ㊢ | U+32A2 | LumpOfRoyalJelly — circled copy: sundry item |

## Species inheritance

| Idiom | Effect |
|-------|--------|
| `EarthElemental ⊑ Elementals` | Species inherits its category (2026-10-10) |
| `FireElemental ⊑ Elementals` | Species inherits its category (2026-10-10) |
| `WaterElemental ⊑ Elementals` | Species inherits its category (2026-10-10) |
| `AirElemental ⊑ Elementals` | Species inherits its category (2026-10-10) |
| `BabyLongWorm ⊑ Worms` | Species inherits its category (2026-10-10) |
| `LongWorm ⊑ Worms` | Species inherits its category (2026-10-10) |
| `BabyPurpleWorm ⊑ Worms` | Species inherits its category (2026-10-10) |
| `PurpleWorm ⊑ Worms` | Species inherits its category (2026-10-10) |
| `MindFlayer ⊑ Mindflayers` | Species inherits its category (2026-10-10) |
| `MasterMindFlayer ⊑ Mindflayers` | Species inherits its category (2026-10-10) |
| `Kobold ⊑ Kobolds` | Species inherits its category (2026-10-10) |
| `LargeKobold ⊑ Kobolds` | Species inherits its category (2026-10-10) |
| `KoboldShaman ⊑ Kobolds` | Species inherits its category (2026-10-10) |
| `KoboldLord ⊑ Kobolds` | Species inherits its category (2026-10-10) |
| `Giant ⊑ Giants` | Species inherits its category (2026-10-10) |
| `StoneGiant ⊑ Giants` | Species inherits its category (2026-10-10) |
| `HillGiant ⊑ Giants` | Species inherits its category (2026-10-10) |
| `FireGiant ⊑ Giants` | Species inherits its category (2026-10-10) |
| `FrostGiant ⊑ Giants` | Species inherits its category (2026-10-10) |
| `Ettin ⊑ Giants` | Species inherits its category (2026-10-10) |
| `StormGiant ⊑ Giants` | Species inherits its category (2026-10-10) |
| `Titan ⊑ Giants` | Species inherits its category (2026-10-10) |
| `VampireBat ⊑ Vampires` | Species inherits its category (2026-10-10) |
| `Vampire ⊑ Vampires` | Species inherits its category (2026-10-10) |
| `VampireLeader ⊑ Vampires` | Species inherits its category (2026-10-10) |
| `VampireLady ⊑ Vampires` | Species inherits its category (2026-10-10) |
| `VampireLord ⊑ Vampires` | Species inherits its category (2026-10-10) |
| `Nosferatu ⊑ Vampires` | Species inherits its category (2026-10-10) |
| `HumanMummy ⊑ Undead` | Species inherits its category (2026-10-10) |
| `ElfMummy ⊑ Undead` | Species inherits its category (2026-10-10) |
| `DwarfMummy ⊑ Undead` | Species inherits its category (2026-10-10) |
| `GnomeMummy ⊑ Undead` | Species inherits its category (2026-10-10) |
| `OrcMummy ⊑ Undead` | Species inherits its category (2026-10-10) |
| `KoboldMummy ⊑ Undead` | Species inherits its category (2026-10-10) |
| `GiantMummy ⊑ Undead` | Species inherits its category (2026-10-10) |
| `EttinMummy ⊑ Undead` | Species inherits its category (2026-10-10) |
| `KoboldZombie ⊑ Undead` | Species inherits its category (2026-10-10) |
| `GnomeZombie ⊑ Undead` | Species inherits its category (2026-10-10) |
| `OrcZombie ⊑ Undead` | Species inherits its category (2026-10-10) |
| `DwarfZombie ⊑ Undead` | Species inherits its category (2026-10-10) |
| `ElfZombie ⊑ Undead` | Species inherits its category (2026-10-10) |
| `HumanZombie ⊑ Undead` | Species inherits its category (2026-10-10) |
| `GiantZombie ⊑ Undead` | Species inherits its category (2026-10-10) |
| `EttinZombie ⊑ Undead` | Species inherits its category (2026-10-10) |
| `Ghoul ⊑ Undead` | Species inherits its category (2026-10-10) |
| `WoodElf ⊑ Elves` | Species inherits its category (2026-10-10) |
| `GreenElf ⊑ Elves` | Species inherits its category (2026-10-10) |
| `GreyElf ⊑ Elves` | Species inherits its category (2026-10-10) |
| `Elf ⊑ Elves` | Species inherits its category (2026-10-10) |
| `ElfNoble ⊑ Elves` | Species inherits its category (2026-10-10) |
| `ElvenMonarch ⊑ Elves` | Species inherits its category (2026-10-10) |
| `BabyDragon ⊑ Dragons` | Species inherits its category (2026-10-10) |
| `Dragon ⊑ Dragons` | Species inherits its category (2026-10-10) |
| `Centipede ⊑ Spiders` | Species inherits its category (2026-10-10) |
| `CaveSpider ⊑ Spiders` | Species inherits its category (2026-10-10) |
| `Scorpion ⊑ Spiders` | Species inherits its category (2026-10-10) |
| `GiantSpider ⊑ Spiders` | Species inherits its category (2026-10-10) |
| `Mastodon ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Mumak ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Baluchitherium ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Titanothere ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Minotaur ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Wumpus ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Trapper ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Owlbear ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Bugbear ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Jabberwock ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Rothe ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `Leocrotta ⊑ Beasts` | Species inherits its category (2026-10-10) |
| `LurkerAbove ⊑ Lurkers` | Species inherits its category (2026-10-10) |
| `Stalker ⊑ Lurkers` | Species inherits its category (2026-10-10) |
| `Shade ⊑ Guises` | Species inherits its category (2026-10-10) |
| `Skeleton ⊑ Guises` | Species inherits its category (2026-10-10) |
| `Foocubus ⊑ Guises` | Species inherits its category (2026-10-10) |
| `MountainNymph ⊑ Guises` | Species inherits its category (2026-10-10) |
| `WoodNymph ⊑ Guises` | Species inherits its category (2026-10-10) |
| `WaterNymph ⊑ Guises` | Species inherits its category (2026-10-10) |
| `MerfolkRoyal ⊑ Merfolk` | Species inherits its category (2026-10-10) |
| `MerfolkNoble ⊑ Merfolk` | Species inherits its category (2026-10-10) |
| `MerfolkWitch ⊑ Merfolk` | Species inherits its category (2026-10-10) |
| `MerfolkCommon ⊑ Merfolk` | Species inherits its category (2026-10-10) |
| `Shopkeeper ⊑ Specials` | Species inherits its category (2026-10-10) |
| `WizardOfYendor ⊑ Specials` | Species inherits its category (2026-10-10) |
| `GrandMaster ⊑ Specials` | Species inherits its category (2026-10-10) |
| `Tin ⊑ Food` | Tin inherits Food — first object species joins the hierarchy (2026-10-10) |
| `AcidBroth ⊑ Soup` | Soup inherits Soup (2026-10-10) |
| `GoldenSoup ⊑ Soup` | Soup inherits Soup (2026-10-10) |
| `StonedSoup ⊑ Soup` | Soup inherits Soup (2026-10-10) |
| `MoldySoup ⊑ Soup` | Soup inherits Soup (2026-10-10) |
| `Manwich ⊑ Soup` | Soup inherits Soup — the human-flesh tin (2026-10-10) |
| `CreamOfAlgaeSoup ⊑ Soup` | Soup inherits Soup (2026-10-10) |
| `ChickenNoodleSoup ⊑ Soup` | Soup inherits Soup (2026-10-10) |
| `RefriedBeans ⊑ Soup` | Soup item inherits Soup — grants teleportation (2026-10-11) |
| `Sushi ⊑ Food` | Sushi inherits Food — the sushi food category (2026-10-10) |
| `CarpSashimi ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `WhaleSashimi ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `EelSashimi ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `SalmonSashimi ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `TunaSashimi ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `CrabSashimi ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `DragonSashimi ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `TurtleSashimi ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `Oyster ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `Uni ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `Gyuniku ⊑ Sushi` | Individual sushi inherits Sushi (2026-10-10) |
| `Asian ⊑ Food` | Asian inherits Food — the Asian food category (2026-10-10) |
| `Ramen ⊑ Asian` | Individual Asian food inherits Asian (2026-10-10) |
| `FortuneCookie ⊑ Asian` | Individual Asian food inherits Asian (2026-10-10) |
| `Kelp ⊑ Asian` | Individual Asian food inherits Asian (2026-10-10) |
| `Dumplings ⊑ Asian` | Individual Asian food inherits Asian (2026-10-10) |
| `BowlOfRice ⊑ Asian` | Individual Asian food inherits Asian (2026-10-10) |
| `SpringRolls ⊑ Asian` | Individual Asian food inherits Asian (2026-10-10) |
| `Tofu ⊑ Asian` | Individual Asian food inherits Asian (2026-10-10) |
| `PreservedEgg ⊑ Asian` | Individual Asian food inherits Asian (2026-10-10) |
| `CantoneseDuck ⊑ Asian` | Individual Asian food inherits Asian (2026-10-10) |
| `Deli ⊑ Food` | Deli inherits Food — the delicatessen food category (2026-10-10) |
| `KelpFrond ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `EucalyptusLeaf ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `CandyBar ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `LembasWafer ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `CramRation ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `FoodRation ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `KRation ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `CRation ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `CloveOfGarlic ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `SprigOfWolfsbane ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `LumpOfRoyalJelly ⊑ Sundry` | Sundry item inherits Sundry (2026-10-10) |
| `Sundry ⊑ Deli` | Sundry is part of Deli (2026-10-10) |
| `Fruit ⊑ Food` | Fruit inherits Food — the fruit food category (2026-10-10) |
| `Apple ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Orange ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Pear ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Melon ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Banana ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Carrot ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Fig ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Lemon ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Lime ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Grapes ⊑ Fruit` | Fruit item inherits Fruit (2026-10-10) |
| `Soup ⊑ Tin` | Soup inherits Tin — the soup category (2026-10-11) |
| `Candy ⊑ Food` | Candy inherits Food — the candy category (2026-10-11) |
| `Goodbar ⊑ Candy` | Goodbar inherits Candy (2026-10-11) |
| `Honee ⊑ Candy` | Honee inherits Candy (2026-10-11) |
| `DRation ⊑ Candy` | DRation inherits Candy (2026-10-11) |
| `DoveBar ⊑ Candy` | DoveBar inherits Candy (2026-10-11) |
| `CrowBar ⊑ Candy` | CrowBar inherits Candy (2026-10-11) |
| `Tomb ⊑ Sundry` | Tomb inherits Sundry (2026-10-11) |
| `Pesto ⊑ Sundry` | Pesto inherits Sundry (2026-10-11) |
| `Spinach ⊑ Soup` | Spinach (NetHack tin filling, Popeye strength) inherits Soup (2026-10-11) |
| `Meat ⊑ Creature` | Meat inherits Creature — the meat category (2026-10-11) |
| `Egg ⊑ Creature` | Egg inherits Creature (2026-10-11) |
| `Creature ⊑ Tin` | Creature inherits Tin — the creature-meat tin category; the category that shuffles monsters as consumables (tins of monster meat) (2026-10-11) |
| `IntegerBounded ⊑ Integer` | IntegerBounded inherits Integer (new 2026-10-15) |
| `IntegerBounded.max ⊑ Integer` | IntegerBounded.max is an Integer (new 2026-10-15) |
| `IntegerBounded.min ⊑ Integer` | IntegerBounded.min is an Integer (new 2026-10-15) |
| `IntegerBounded.epsilon ⊑ Integer` | IntegerBounded.epsilon is an Integer (new 2026-10-15) |
| `IntegerBounded.nabla` — NOTE | IntegerBounded.nabla enforces bounded gets and sets (new 2026-10-15) |
| `IntegerBounded.nabla ⊑ Interpreter` | IntegerBounded.nabla is an Interpreter (new 2026-10-15) |
| `Angle ⊑ IntegerBounded` | Angle inherits IntegerBounded (new 2026-10-15) |
| `VirtualHorizontal ⊑ Angle` | VirtualHorizontal inherits Angle (new 2026-10-15) |
| `VirtualVertical ⊑ Angle` | VirtualVertical inherits Angle (new 2026-10-15) |
| `VirtualDistance ⊑ IntegerBounded` | VirtualDistance inherits IntegerBounded (new 2026-10-15) |

| Interpreter  | ‽     | U+203D    | Interpreter — the Wuxia interpreter (new 2026-10-15) |
| Angle        | ⦵     | U+29B5    | Angle — a VR angle (theta/phi) (new 2026-10-15) |
| VirtualHorizontal | ⧓ | U+29D3 | VirtualHorizontal — horizontal angle in VirtualSpace (new 2026-10-15) |
| VirtualVertical | ⧗ | U+29D7 | VirtualVertical — vertical angle in VirtualSpace (new 2026-10-15) |
| VirtualDistance | ⟰ | U+27F0 | VirtualDistance — distance in VirtualSpace, 0-512 (new 2026-10-15) |
| `Meat` — NOTE | Meat stays empty till use — populated by the Creature monster-shuffle at runtime (2026-10-11) |
| `Egg` — NOTE | Egg stays empty till use — populated by the Creature monster-shuffle at runtime (2026-10-11) |
