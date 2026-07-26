---
type: project
status: in-progress
tags:
  - example
---
Write a one-pager on remote-work policy for the team: current practice, two options, a recommendation.

A second example project, here to show that `01 Projects/Projects.base` lists them all as cards.

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
