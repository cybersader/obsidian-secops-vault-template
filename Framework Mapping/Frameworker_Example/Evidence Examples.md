---
aliases: 
tags: 
date created: 2025-01-13T14:01:26-05:00
date modified: 2025-01-13T14:01:32-05:00
---
# Dataview

## Markdown Style Internal Links

### EX - Beginning of Line

framework_here.applies_to:: [ID ??](ID%20??.md)

- ^^^ BUG - automatically tries to use Wikilink syntax

### EX - Dataview Inline Tag w/Parentheses (Hides Key)

-  A DLP solution has been implemented by the team (framework_here.applies_to:: [ID ??](ID%20??.md))

- ^^^ Dataview inline tag with parentheses + Omnisearch (ALT + ENTER) seems to work
	- Link matches up correctly

### EX - Dataview Inline Tag w/Square Brackets

- A DLP solution has been implemented by the team [framework_here.applies_to:: [ID ??](ID%20??.md)]

- ^^^ Dataview inline tag with square brackets + Omnisearch (ALT + ENTER) seems broken
	- Link doesn't work and creates new page with URL encoding in name

## Wikilinks Style Internal Links

### EX - Beginning of Line

framework_here.applies_to:: [[ID ??]]

- ^^^ BUG - automatically tries to use Wikilink syntax

### EX - Dataview Inline Tag w/Parentheses (Hides Key)

-  A DLP solution has been implemented by the team (framework_here.applies_to:: [[ID ??]])

- ^^^ Dataview inline tag with parentheses + Omnisearch (ALT + ENTER) seems to work
	- Link matches up correctly

### EX - Dataview Inline Tag w/Square Brackets

- A DLP solution has been implemented by the team [framework_here.applies_to:: [[ID ??]]]

- ^^^ Dataview inline tag with square brackets + Omnisearch (ALT + ENTER) seems broken
	- Link doesn't work and creates new page with URL encoding in name

# Graph Type Links

## Markdown Style

### No Metadata - just the link

[framework_here:: [framework_note](link_to_framework_note_here)]

### JSON Metadata without dot notation for tag

[framework_here:: [framework_note](link_to_framework_note_here){sufficent: True, control: True, reviewer: "Person_1"}]

### Dot notation-based keys only

#### Example of reviewer for all outgoing connections to "frameworks"

[framework_here.reviewer:: "Person_1"]
[framework_here.reviewer:: 1{"Person_1"}]

### Dot notation and JSON metadata

#### Example of specific reviewer for a particular frameworker

[framework_here.reviewer:: [framework_note](link_to_framework_note_here){"Person_1"}]  // a value only in curly brackets means the value of the dot notation key - the value can be an object, a list/array, a number, None, or a string I'm assuming