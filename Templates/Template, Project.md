---
type: project
status: in-progress
---

# Project Name

One-line description of the project and its end state.

## Related notes

-

## Meetings

```base
filters:
  and:
    - type == "meeting"
    - project.contains(this.file.asLink())
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
