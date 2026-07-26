<%*
const title = await tp.system.prompt("Meeting title");
if (title) { await tp.file.rename(tp.date.now("YYYY-MM-DD") + " " + title); }
-%>
---
type: meeting
date: <% tp.date.now("YYYY-MM-DD") %>
related-to: ""
---

## Agenda / Prep Notes
- 
## Meeting Notes
- 
