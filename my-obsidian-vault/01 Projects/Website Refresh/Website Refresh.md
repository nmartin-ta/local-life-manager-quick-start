---
type: project
status: in-progress
tags:
  - example
---
Refresh the team website: new structure, updated copy, launch by end of quarter.

Example project note #example. A project's page is where you keep the short description and the links; the tables below fill themselves in from whatever points here with `related-to`. The `initiate` skill sets up pages like this for your own projects, or you can ask Claude for one any time.

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
