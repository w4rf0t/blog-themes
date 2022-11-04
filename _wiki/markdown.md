---
layout: wiki
title: Markdown
cate1: Copywriting
cate2:
description: An example of common Markdown syntax.
keywords: Markdown
mermaid: true
sequence: true
flow: true
mathjax: true
mindmap: true
---

**Directory**

* TOC
{:toc}

### Hyperlink

````
[Reliable-ing](https://mazhuang.org)

<https://mazhuang.org>
````

[Reliable-ing](https://mazhuang.org)

<https://mazhuang.org>

### list

````
1. Ordered list items 1

2. Ordered list items 2

3. Ordered list items 3
````

1. Ordered list items 1

2. Ordered list items 2

3. Ordered list items 3

````
* unordered list entry 1

* unordered list entry 2

* unordered list entry 3
````

* unordered list entry 1

* unordered list entry 2

* unordered list entry 3

````
- [x] Task List 1
- [ ] Task List 2
````

- [x] Task List 1
- [ ] Task List 2

### emphasize

````
~~strike out~~

**With black**

*italic*
````

~~strike out~~

**With black**

*italic*

### Title

````
# first level title
## Secondary title
### Level 3 heading
#### Level 4 heading
##### Level 5 heading
###### Level 6 heading
````

Tips: Add a space between `#` and the title.

### sheet

````
| HEADER1 | HEADER2 | HEADER3 | HEADER4 |
| ------- | :------ | :-----: | ------: |
| content | content | content | content |
````

| HEADER1 | HEADER2 | HEADER3 | HEADER4 |
| ------- | :------ | :-----: | ------: |
| content | content | content | content |

1. :----- means left-aligned
2. :----: means center alignment
3. -----: means right-aligned

### code block

````python
print 'Hello, World!'
````

1. list item1

2. list item2

   ````python
   print 'hello'
   ````

### picture

````
![This site favicon](/favicon.ico)
````

![This site favicon](/favicon.ico)

### Anchor

````
* [Directory](#Directory)
````

* [Directory](#Directory)

### Inline Attribute

Span Inline Attribute details reference <https://kramdown.gettalong.org/syntax.html#span-ials>

Block Inline Attribute details refer to <https://kramdown.gettalong.org/syntax.html#block-ials>

Add classes, ids, inline styles, etc. to blocks/elements:

````
![This site favicon](/favicon.ico){:.center}

Hello, *world*{:#world}

Hello, *world*{: style="color:red"}
````

![This site favicon](/favicon.ico){:.center}

Hello, *world*{:#world}

Hello, *world*{: style="color:red"}

Combined with custom styles, some scenarios are more useful.

### Emoji

:camel:
:blush:
:smile:

### Footnotes

This is a text with footnote[^1].

### mermaid

<div class="mermaid">
sequenceDiagram
    Alice-->>John: Hello John, how are you?
    John-->>Alice: Great!
</div>

### sequence

````sequence
Andrew->China: Says Hello
Note right of China: China thinks\nabout it
China-->Andrew: How are you?
Andrew->>China: I am good thanks!
````

### flowchart

````flow
st=>start: Start
e=>end
op1=>operation: My Operation
sub1=>subroutine: My Subroutine
cond=>condition: Yes
or No?
io=>inputoutput: catch something...

st->op1->cond
cond(yes)->io->e
cond(no)->sub1(right)->op1
````

### mathjax

When $$(a \ne 0)$$, there are two solutions to $$(ax^2 + bx + c = 0)$$ and they are

$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$

### mindmap

```mindmap
#topic
## topic2
### topic2.1
### topic2.2
## topic3
<!--Note-->
This is a remark
<!--/Note-->
### topic3.1
### topic3.2
#### topic3.2.1
#### topic3.2.2
#### topic3.2.3
#### topic3.2.4
#### topic3.2.5
### topic3.4
### topic3.5
### topic3.6
````

[^1]: Here is the footnote 1 definition.