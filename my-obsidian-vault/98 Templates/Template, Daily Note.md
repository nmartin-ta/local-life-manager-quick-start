---
type: daily-note
---
# <% moment(tp.file.title, "YYYY-MM-DD").format("dddd, MMMM D, YYYY") %>

<< [[<% tp.date.now("YYYY-MM-DD", -1, tp.file.title, "YYYY-MM-DD") %>|← Yesterday]] | [[<% tp.date.now("YYYY-MM-DD", 1, tp.file.title, "YYYY-MM-DD") %>|Tomorrow →]] >>

## Today's Agenda
-

## Notes
```meta-bind-button
label: Insert Timestamp
style: primary
actions:
  - type: insertIntoNote
    templater: true
    value: 80 Templates/Template, Time Log Entry.md
    line: selfEnd + 2
```

%% do what needs to be done to make insert timestamp work as in my other vaults %%
