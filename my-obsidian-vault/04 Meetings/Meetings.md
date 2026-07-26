---
type: moc
---
All meeting notes live in this folder. Press the button to create one; it asks for a title and fills in today's date. Set a meeting's `related-to` property to a project and the meeting turns up on that project's page without any further filing.

```meta-bind-button
label: New meeting note
icon: plus
style: primary
action:
  type: templaterCreateNote
  templateFile: 98 Templates/Template, Meeting Note.md
  folderPath: 04 Meetings
  openNote: true
```

## All meetings

```base
filters:
  and:
    - type == "meeting"
views:
  - type: table
    name: All meetings
    order:
      - file.name
      - date
      - note["related-to"]
    sort:
      - property: date
        direction: DESC
```
