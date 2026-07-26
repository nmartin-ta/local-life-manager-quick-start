---
type: project
status: in-progress
tags:
  - example
---
Refresh the team website: new structure, updated copy, launch by end of quarter.

This is an example project note — a "map of content" for one project. Keep a short description up top, capture links to relevant notes below, and the table underneath automatically lists every meeting linked to this project. Ask Claude to create pages like this for your real projects (the `personalize` skill does it for you).

## Related notes

- [[+Professional Development]] — example of linking a project to an area

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

## Tasks

```base
filters:
  and:
    - file.hasTag("task")
    - related-to.contains(this.file.asLink())
    - status != "done"
views:
  - type: table
    name: Tasks
    order:
      - file.name
      - due
      - scheduled
      - status
    sort:
      - property: due
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
