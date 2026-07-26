---
type: moc
---

# Meetings

All meeting notes live in this folder. Press the button to create one — you'll be asked for a title, and today's date is filled in automatically. Link each meeting to a project by setting its `related-to` property, and it will appear on that project's page automatically.

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
      - related-to
    sort:
      - property: date
        direction: DESC
```
