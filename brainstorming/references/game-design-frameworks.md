# Design frameworks for critiquing a concept

Yardsticks to reach for when a concept needs an outside standard rather than
another opinion from you. Use them to land a critique on one question the user
can answer — never to decorate the reply.

## Schell's lenses — pull the list from the source, mind the edition

### Retrieval recipe

The official *Deck of Lenses* site is a JS SPA: it renders the menu shell and
no card list, so scraping the DOM gives you navigation and nothing else. Find
the data file instead of fighting the render:

1. Load the page, then read `performance.getEntriesByType('resource')` for a
   data path (it is `assets/json/lenses.json`).
2. `fetch()` that path **inside the page's own JS** — same origin, no CORS, no
   auth. Despite the `.json` extension it returns XML: `<lens>` blocks with
   `<index>`, `<title>`, `<suit>`, a description and the question list.
3. Parse by splitting on `<lens name="` rather than a strict regex — whitespace
   and entities (`&apos;`) vary between blocks.

### Numbering trap

This is how you end up citing a lens the user has never heard of.

| Edition | Count | Emergence | Simplicity / Complexity |
|---|---|---|---|
| 1st (2008) | 100 | #23 | #42 |
| 2nd (2014) + Deck of Lenses (10th anniv.) | 113 | **#30** | **#48** |
| 3rd (2022) | 100+ | renumbered | renumbered |

Third-party notes are mixed — many Chinese blog series follow the 1st edition.
When the user names a number, confirm the edition from *their* number against
this table before you discuss it, and say which edition you are quoting.

### The two lenses that gate an emergence / systems concept

**#30 Emergence (suit: Game)** — five counts that make "is it emergent"
measurable instead of arguable:

1. How many **verbs** does the player have?
2. How many **objects** can each verb act on?
3. How many distinct **paths** to a goal?
4. How many **subjects** does the player control?
5. How do **side effects** change later constraints?

The first three scale the combination space (the room an unscripted outcome
needs). The last two are the guard: a zero on *subjects controlled* means the
concept has made the player a spectator — report that as the defect, by that
name.

**#48 Simplicity / Complexity (suit: Game)** — separates **innate complexity**
(rules the player must memorise) from **emergent complexity** (patterns that
grow out of simple rules interacting). Four checks: what innate complexity do
I have; can it be converted into emergent complexity; is emergent complexity
actually appearing, and if not why not; **is anything too simple**.

### How to run them

Score the concept as a one-row-per-question table with a verdict column, then
read the pattern instead of the individual rows. The last question of #48 is
where a systems-heavy concept usually fails — many rules, few things for the
player to do — and naming it as *that question* converts "it isn't fun" from a
mood into a fixable list the user can answer in one round.
