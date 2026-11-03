---
layout: theme
title: "Readable Resume"
category: theme
author: "Super Lede"
thumbnail: "readable-resume.png"
homepage: "https://readableresume.com"
download: "https://github.com/supertj/typora-readable-resume/archive/refs/heads/main.zip"
description: "A one-page resume theme with the Classic layout from ReadableResume: Georgia, section headings in capitals over a thin rule, and dates on the right margin. Exports a single-column PDF on Letter or A4."
tags: [light, resume, cv, print, serif]
built-in: false
typora-root-url: ../../
---

# Readable Resume

A theme for writing a one-page resume in Typora. You type headings and bullets
as usual and export a PDF with your name centered at the top, section headings
in capitals over a thin rule, and places and dates on the right margin. The
layout is the Classic template from
[ReadableResume](https://readableresume.com), where the same design is
available for Google Docs and Word.

![The sample resume in the editor](/media/theme/readable-resume/editor.png)

The PDF is a single column with no tables, text boxes or icons, and the text
comes out in the order you read it. That's the text applicant tracking systems
parse.

## Writing a resume with it

| You type | On the page |
|---|---|
| `# Your Name` | Your name, centered |
| The paragraph right after it | The contact line, centered |
| `## Experience` | A section heading in capitals over a rule |
| `### Company` and text in backticks | A bold line, with the backtick text on the right margin |
| `#### Job Title` and text in backticks | An italic line, with the backtick text on the right margin |
| `- ` | A bullet point |

```markdown
### Harlan Quay Capital Partners `New York, NY`

#### Investment Banking Analyst Intern `Jun 2025 – Aug 2025`

- Built three-statement models for two consumer retail clients
```

Backticks mark what goes on the right. Typora shows them only while the cursor
is in that text:

![The backticks around the dates show while the cursor is in them](/media/theme/readable-resume/backticks.png)

A dashed line marked "Page 2" is a guide to where the first page ends, drawn for
A4's width and Letter's height. If everything is above it, the resume fits
on one page of either size. The line only shows in the editor.

## Exporting

Pick A4 or Letter under Preferences → Export → PDF and leave the margins at
the default 16 mm. This is what the sample looks like on Letter:

![The exported PDF on US Letter](/media/theme/readable-resume/pdf-letter.png)

## Installation

1. Download the zip and unpack it.
2. Open Typora's preferences and, under Appearance, click Open Theme Folder.
3. Copy `readable-resume.css` into that folder.
4. Restart Typora and choose Readable Resume from the Themes menu.

The zip also has `sample-resume.md` to start from. The theme styles the
document only; menus and the sidebar keep Typora's default look. It's a light
theme, with no dark version.
