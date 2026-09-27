---
title: Search
nav_order: 5
---

# Search

Type in the search box at the top of the explorer, every term has to match.

- `Door` - Names containing "door"
- `name:"Main Door"` - Quotes for names with spaces
- `class:BasePart` - Everything that `IsA` BasePart
- `tag:Enemy` - Everything with that tag
- `attr:Health` - Everything with that attribute, also `attr:Health=100`, `attr:Health>50`, `attr:Team~=Red`
- `prop:Anchored=false` - Compares a property the same way, e.g. `prop:Material=Neon`, `prop:Transparency>0.5`
- `path:workspace.Map` - The instance at that path
- `parent:workspace.Map` - Its children
- `in:workspace.Map` - Its descendants

You can combine them, e.g. `class:Light in:workspace.Map` or `class:Part attr:Team=Red`. The server-only folders you expose are searched too.
