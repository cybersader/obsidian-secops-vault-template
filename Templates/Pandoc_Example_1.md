---
aliases: []
tags: []
title: PANDOC_EXAMPLE_1
abstract: ' `<w:p><w:r><w:br w:type=\"page\"/></w:r></w:p>`{=openxml}'
Author: author_here
date: 
logo: 
header-includes:
  - \usepackage{graphicx}
  - \graphicspath{ {./images/} }
---

# Template Heading

This is a markdown template to convert documents to .docx using Pandoc.

## Example Section

Add your content here. You can include:

- **Text:** Markdown formatted text
- **Images:** `![Alt text](image.png)`
- **Tables:**

|Header 1|Header 2|
|---|---|
|Content 1|Content 2|

## YAML Frontmatter

The YAML block at the top specifies metadata for your document:

- `title`: Title of the document
- `author`: Author's name
- `date`: Date of publication
- `logo`: Path to a logo file

## Customization with Pandoc

You can use a custom reference .docx file to define styles. Create a .docx file with the desired formatting, then use the following command:

```
pandoc input.md -o output.docx --reference-doc=custom-reference.docx
```

Ensure your YAML and markdown content aligns with the reference document styles.