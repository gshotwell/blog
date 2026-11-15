# Writing recipes for shotwell.ca/recipes

Recipes here are written by an LLM from Gordon's notes, a conversation, or a
source recipe he has adapted. Follow this format exactly so every page reads the
same and the listing at `/recipes/` stays useful.

## Files

- One folder per recipe: `recipes/<slug>/index.qmd`, where the slug is
  lowercase and hyphenated (`no-knead-bread`). The URL is
  `shotwell.ca/recipes/<slug>/`.
- Photos, if any, go in the same folder (`recipes/<slug>/photo.jpg`) and are
  set as `image:`.
- Don't edit `recipes/index.qmd`; the listing picks up new folders on its own.

## Front matter

```yaml
---
title: "No-Knead Bread"            # plain name, no adjectives like "Best"
description: "One sentence: what it is and why you'd make it."
date: 2026-11-15                   # date added
categories: [bread, baking]        # 1–3, lowercase, reuse existing ones
servings: "1 loaf"                 # string; include the unit
active-time: "20 min"
total-time: "14 hr"
source: "Adapted from Jim Lahey"   # optional; omit if original
image: photo.jpg                   # optional
---
```

Check existing categories first (`grep -h -A3 categories recipes/*/index.qmd`) and reuse
them. Current conventions: course or type (`bread`, `soup`, `dinner`,
`dessert`, `breakfast`, `sauce`) plus at most one technique or dietary tag
(`baking`, `vegetarian`).

## Body

Use these sections, in this order, with these exact headings. Skip **Notes**
if there's nothing worth saying.

```markdown
**Serves** {{< meta servings >}} · **Active** {{< meta active-time >}} · **Total** {{< meta total-time >}}

A short paragraph (2–4 sentences): what this is, when Gordon makes it, and
anything unusual about the method. No life story, no "nothing beats…".

## Ingredients

- 500 g (4 cups) bread flour
- 10 g (2 tsp) kosher salt

## Method

1. One action per step. Put times and temperatures in the step.
2. Say what "done" looks like, not just how long it takes.

## Notes

- Substitutions, make-ahead, storage, and what went wrong last time.
```

## Style rules

- **Weights first, volumes in parentheses** for anything baked or where
  precision matters: `500 g (4 cups) flour`. Small amounts can be volume only:
  `1 tsp cumin`. Liquids in ml with cups in parentheses.
- **Celsius first, Fahrenheit in parentheses**: `230 °C (450 °F)`.
- Ingredients are listed in the order they're used. Group with bold
  sub-labels (`**For the sauce**`) only when there are distinct components.
- Prep goes in the ingredient line: `1 onion, finely diced`.
- Steps are imperative and short. Give doneness cues ("until the edges are
  deep brown and it smells nutty, about 4 min").
- Canadian spelling. Plain, direct tone; see `../gordon-style-guide.md`.
- Don't invent claims about Gordon's experience. If the notes don't say how
  he serves it or what he changed, leave it out.
- Test it renders: `quarto render recipes/<slug>/index.qmd`.
