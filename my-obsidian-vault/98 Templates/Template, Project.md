---
type: project
status: in-progress
---

# Project Name

One-line description of the project and its end state.

## Related notes

```base
filters:
  and:
    - related-to.contains(this.file.asLink())
    - type != "meeting"
views:
  - type: table
    name: Related notes
    order:
      - file.name
    sort:
      - property: file.name
        direction: ASC
```

## Meetings

```base
filters:
  and:
    - type == "meeting"
    - related-to.contains(this.file.asLink())
views:
  - type: table
    name: Meetings
    order:
      - file.name
      - date
    sort:
      - property: date
        direction: DESC
```
