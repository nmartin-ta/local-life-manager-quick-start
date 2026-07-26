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
    - file.hasLink(this.file)
    - type != "meeting"
    - '!file.hasTag("task")'
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
    - file.hasLink(this.file)
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
    - file.hasLink(this.file)
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
