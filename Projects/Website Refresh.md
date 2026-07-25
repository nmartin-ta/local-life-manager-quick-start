---
type: project
status: in-progress
tags:
  - example
---

# Website Refresh

Refresh the team website: new structure, updated copy, launch by end of quarter.

This is an example project note — a "map of content" for one project. Keep a short description up top, capture links to relevant notes below, and the table underneath automatically lists every meeting linked to this project. Ask Claude to create pages like this for your real projects (the `personalize` skill does it for you).

## Related notes

- [[Professional Development]] — example of linking a project to an area

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
