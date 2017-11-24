---
layout: post
title: Markdown quick reference
description: Markdown syntax reference
modified: 
tags: [Mardown]
image:
  feature: markdown1-4.png
---

# Markdown quick reference
> See the Markdown page for instructions on enabling Markdown for posts, pages and comments on your blog, and for more detailed information about using Markdown.

## Syntax

### Emphasis

`*This text will be italic*`
*This text will be italic*

`_This will also be italic_`
_This will also be italic_

`**This text will be bold**`
**This text will be bold**

`__This will also be bold__`
__This will also be bold__

`_You **can** combine them_`
_You **can** combine them_


### Inline Links

`A [link](https://www.google.com "Google").`A [link](https://www.google.com "Google").

### Referenced Links

    Some text with [a link][1] and
    another [link][2].
    
    [1]: http://example.com/ "Title"
    [2]: http://example.org/ "Title"

Some text with [a link][1] and
another [link][2].

[1]: http://example.com/ "Title"
[2]: http://example.org/ "Title"

### Inline Images

`Logo: ![favicon](https://omv6w8gwo.qnssl.com/favicon.ico "Title")`

Logo: ![favicon](https://omv6w8gwo.qnssl.com/favicon.ico "Title")

### Linked Images

`Linked logo: [![Fython](https://omv6w8gwo.qnssl.com/favicon.ico "Fython")](https://www.google.com/ "Fython")`

Linked logo: [![Fython](https://omv6w8gwo.qnssl.com/favicon.ico "Fython")](https://www.google.com/ "Fython")

### Unordered Lists

    * Item
    * Item
    - Item
    - Item

* Item
* Item
- Item
- Item

### Ordered Lists

    1. Item
    2. Item
    3. Item

1. Item
2. Item
3. Item

### Blockquotes

    > Quoted text.
    > > Quoted quote.
    
    > * Quoted 
    > * List

> Quoted text.
> > Quoted quote.

> * Quoted 
> * List

### Inline Code

```
`This is code` This is text
``` 

`This is code` This is text

### Code block

```
    This is a
    piece of code 
    in a block
```

Notice Indent 

    This is a
    piece of code
    in a block


### Heads

    # Header 1
    ## Header 2
    ### Header 3 
    #### Header 4
    ##### Header 5
    ###### Header 6
    
# Header 1
## Header 2
### Header 3 
#### Header 4
##### Header 5
###### Header 6

---

## GitHub Flavored Markdown

### Syntax highlighting

    ```python
    def foo():
        if not bar:
            return True
    ```

Here’s an example

```python
def foo():
    if not bar:
        return True
```

### Task List

```
- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item
```

- [x] @mentions, #refs, [links](), **formatting**, and <del>tags</del> supported
- [x] list syntax required (any unordered or ordered list supported)
- [x] this is a complete item
- [ ] this is an incomplete item

### Tables

You can create tables by assembling a list of words and dividing them with hyphens - (for the first row), and then separating each column with a pipe

First Header | Second Header
------------ | -------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column
{: rules="groups"}

### Strikethrough

`~~this~~`

Any word wrapped with two tildes (like ~~this~~) will appear crossed out.
