---
aliases: []
tags: []
date created: 2024-12-20T13:11:20-05:00
date modified: 2025-01-13T14:10:13-05:00
---

# Examples of Links

There are precisely 22 examples in this file:
- 8 graph link defaults
- 9 to ID 12
- 2 to ID 13
- 1 to ID 14

framework_here.reviewer:: "Person_1"
  [framework_here.applies_to:: [ID 12](ID%2012.md)]
  (framework_here.applies_to:: [[ID 13]] {"sufficient": true, "control": true})
  framework_here.reviewed:: [[ID 12]]
  [framework_here.approved:: True]
  (framework_here.score:: 9)
  [framework_here.score:: [[ID 13]] {9}]
  - [framework_here.applies_to:: [[ID 14]] {"test": 123}]
framework_here.debug:: "NoLinkJustQuoted"
  [framework_here.score:: [[ID 13]]]
  (framework_here:: [ID 12](ID%2012.md))
framework_here.applies_to:: [ID 12](ID%2012.md) 
-  A DLP solution has been implemented by the team (framework_here.applies_to:: [ID 12](ID%2012.md))
- A DLP solution has been implemented by the team [framework_here.applies_to:: [ID 12](ID%2012.md)]
framework_here.applies_to:: [[ID 12]]
-  A DLP solution has been implemented by the team (framework_here.applies_to:: [[ID 12]])
[framework_here.applies_to:: [[ID 12]]]
[framework_here:: [framework_note](link_to_framework_note_here)]
[framework_here:: [framework_note](link_to_framework_note_here){sufficent: True, control: True, reviewer: "Person_1"}]
[framework_here.reviewer:: "Person_1"]
[framework_here.reviewer:: 1{"Person_1"}]
[framework_here.reviewer:: [framework_note](link_to_framework_note_here){"Person_1"}]