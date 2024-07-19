---
title: Introduction to Markdown
date: 2024-07-19
authors: [fstueber]
slug: markdown-explained
description: >
  Introduction to the basic concepts of Markdown.
categories:
  - Standards
---

# Introduction to Markdown

Markdown is a markup language designed to make text formatting simple and readable. It is widely used for creating documentation, blog posts, and other texts where simple formatting suffices. This blog post provides an in-depth introduction to Markdown.

<!-- more -->

## Starting Point

[Markdown](https://daringfireball.net/projects/markdown/) was developed in 2004 by [John Gruber](https://github.com/gruber) in collaboration with [Aaron Swartz](https://en.wikipedia.org/wiki/Aaron_Swartz). The goal was to create a simple markup language that is both readable and writable without the need for complex HTML tags. The name "Markdown" refers to the process of "dumbing down" the markup language to make it more user-friendly.

Markdown files are text files and typically have the `.md` or `.markdown` extension.

## Basic Syntax

Here are the basic elements of Markdown.

### Headings

Headings are marked with the `#` symbol. The number of `#` symbols determines the level of the heading.

Examples:

```
# H1 Heading
## H2 Heading
### H3 Heading
#### H4 Heading
##### H5 Heading
###### H6 Heading
```

### Bold and Italic

Text can be formatted as **bold** or *italic*.

Examples:

```
*italic* or _italic_
**bold** or __bold__
***bold and italic*** or ___bold and italic___
```

### Lists

There are unordered and ordered lists.

Examples:

```
This is an unordered list:
- Item one
- Item two
    - Subitem

This is an ordered list:
1. First item
2. Second item
    1. Subitem
```

### Links

Links are written in square brackets `[text]` and round brackets `(URL)`.

Example:

```
[OpenPotato](https://www.openpotato.org)
```

### Images

Images are inserted similarly to links, but with an exclamation mark `!` in front.

Example:

```
![OpenPotato Logo](https://www.openpotato.org/en/assets/logos/logo.svg)
```

### Blockquotes

Blockquotes are marked with `>`.

Example:

```
> This is a blockquote.
```

### Code

For inline code, use backticks `` ` ``.

Example:

```
This is `inline code`.
```

Code blocks can be created with three backticks or by indenting the text with four spaces.

Example:

````
``` 
def hello_world():
    print("Hello World")
```
````

### Tables

Tables can be created with `|` and `-`.

Example:

```
| Header 1      | Header 2      |
| ------------- | ------------- |
| Cell 1        | Cell 2        |
| Cell 3        | Cell 4        |
```

### Paragraphs

Paragraphs in Markdown are separated by one or more blank lines. A blank line between two text blocks creates two separate paragraphs.

Example:

```
This is the first paragraph.

This is the second paragraph.
```

### Line Breaks

In Markdown, a single line break (Enter key) within a paragraph is generally ignored. To actually create a line break, you need to add two spaces at the end of the line and then press Enter.

Example (note the two spaces at the end of the first line):

```
This is the first line.  
This is the second line.
```

Another way to enforce a line break is by using the HTML `<br>` tag (see also the section on *Inline HTML*). This is particularly useful when writing more complex documents or ensuring that the line break is rendered correctly regardless of the Markdown parser used.

Example:

```
This is the first line.<br>This is the second line.
```

### Escape Syntax

In Markdown, certain characters and sequences have special meanings and are used for formatting text, such as `*` for italic text or `#` for headings. Sometimes, however, you want to display these characters as normal text. This is where escape syntax comes into play, allowing you to neutralize the special meaning of these characters.

To display a special character in Markdown as a normal character, use the backslash (`\`). The backslash signals to Markdown that the following character should be treated as a normal character.

Examples:

- **Asterisk (\*)**:
  ```
  \*This text is not italic\*
  ```
  Will be rendered as: \*This text is not italic\*

- **Underscore (\_)**:
  ```
  \_This text is not italic\_
  ```
  Will be rendered as: \_This text is not italic\_

- **Hash (\#)**:
  ```
  \# This is not a heading
  ```
  Will be rendered as: \# This is not a heading

- **Backtick (\`)**:
  ```
  \`This is not inline code\`
  ```
  Will be rendered as: \`This is not inline code\`

- **Backslash (\\)**:
  ```
  This is a backslash: \\
  ```
  Will be rendered as: This is a backslash: \\

### Horizontal Rules

Horizontal rules or lines can be used to visually separate content.

There are several ways to create a horizontal line in Markdown. These methods include using three or more hyphens (`-`), underscores (`_`), or asterisks (`*`). Optional spaces can be added between these characters.

Example with hyphens:

```
This is text above the line.
---
This is text below the line.
```

Example with asterisks and spaces:

```
This is text above the line.

* * *

This is text below the line.
```

### Inline HTML

Markdown files are usually rendered as HTML, and any valid HTML tag can be used within a Markdown document. This allows for advanced formatting that is not possible with native Markdown syntax.

Example:

```
This is a normal paragraph in Markdown.

<div style="color: red;">This text is red and within a div tag.</div>

<p>This is a paragraph in HTML format.</p>
```

## Extensions and Dialects

Markdown has several dialects and extensions that offer additional functionality. Here are two examples:

### GitHub Flavored Markdown (GFM)

[GitHub](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) has extended Markdown with some useful features.

#### Task Lists

Task lists can be created with `[ ]` and `[x]`.

Example:

```
- [x] Task 1
- [ ] Task 2
```

#### Syntax Highlighting

GitHub supports syntax highlighting for various programming languages in code blocks.

Here is an example for Python code:

````
```python
def hello_world():
    print("Hello World")
```
````

#### Strikethrough

Strikethrough text can be created with `~~`.

Example:

```
~~This text is strikethrough~~
```

### Pandoc Markdown

[Pandoc](https://pandoc.org/MANUAL.html#pandocs-markdown) is a tool for converting Markdown into many different formats. It extends Markdown with additional features, such as footnotes and mathematical formulas.

#### Footnotes

A footnote is a source reference or note that appears at the bottom of a page.

Example:

```
This is a sample text with a footnote[^1].

[^1]: This is the footnote.
```

#### Mathematical Formulas

Mathematical formulas can be inserted in Pandoc using LaTeX syntax.

Examples:

```
An inline math example: \(E = mc^2\)

A block math example:
$$
E = mc^2
$$
```

### Cheatsheet

For a comprehensive overview of Markdown, you can refer to a useful [Markdown Cheatsheet](https://github.com/lifeparticle/Markdown-Cheatsheet/blob/main/README.md) that covers many additional nuances.