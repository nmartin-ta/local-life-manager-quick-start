---
type: moc
---

# Projects

One folder per project; each has a `+` note like this one as its front page.

```base
filters:
  and:
    - type == "project"
    - !file.inFolder("98 Templates")
views:
  - type: table
    name: All projects
    order:
      - file.name
      - status
    sort:
      - property: file.name
        direction: ASC
```
