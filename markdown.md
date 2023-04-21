# Markdown

[Markdown](https://en.wikipedia.org/wiki/Markdown) is a lightweight markup language with plain-text-formatting syntax.
Since the initial description of Markdown contained ambiguities and unanswered questions, the implementations that appeared over the years have subtle differences and many come with syntax extensions.
Mathconf.org use the javascript parser [markdown-it](https://github.com/markdown-it/markdown-it).

## Online editor

You can experiment with the textile syntax using the [official playground](https://markdown-it.github.io/).

## Documentation

The syntax is based on the [CommonMark](https://commonmark.org/help/) version.
It is also compatible with the [GFM extension](https://guides.github.com/features/mastering-markdown/).

## Some examples

Here we present some elements of the syntax.

### titles

| Markdown           | Result                |
|:-------------------|:----------------------|
| `# Title`          | <h1>Title</h1>        |
| `## Subtitle`      | <h2>Subtitle</h2>     |
| `### Sub-subtitle` | <h3>Sub-subtitle</h3> |

### Text, links, images

| Markdown                                | Result                                              |
|:----------------------------------------|:----------------------------------------------------|
| `**bold**`                              | <strong>bold</strong>                               |
| `*italic*` or  `_italic_`               | <em>italic</em>                                     |
| `***combined***` or `**_combined_**`    | <strong><em>combined</em></strong>                  |
| `[INSMI](http://www.cnrs.fr/insmi)`     | <a href="http://www.cnrs.fr/insmi">INSMI</a>        |
| `![Zen](https://imgur.com/qzNsLbB.jpg)` | <img src="https://imgur.com/qzNsLbB.jpg" alt="Zen"> |

## Lists

## unordered

| Markdown                                                                                   | Result                                                                                           |
|:-------------------------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------|
| `- Item A`<br>&nbsp;&nbsp;`- Item A1`<br>&nbsp;`- Item A2`<br>`- Item B`<br>`- Item C`<br> | <ul><li>Item A <ul><li>Item A1</li><li>Item A2</li></ul></li><li>Item B</li><li>Item C</li></ul> |

You can use `+` or `*` in place of `-`.

## Numbered

| Markdown                                                                                                             | Result                                                                                              |
|:---------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------|
| `1. Item 1`<br>&nbsp;&nbsp;&nbsp;`1. Item 1.i`<br>&nbsp;&nbsp;&nbsp;`1. Item 1.ii`<br>`1. Item 2`<br>`1. Item 3`<br> | <ol><li>Item 1 <ol><li>Item 1.i</li><li>Item 1.ii</li></ol></li><li>Item 2</li><li>Item 3</li></ol> |

For the nested numbered list you should indent at least 3 spaces.

## Comments

You can use the standard HTML comments that are included in the resulting code, but are not displayed.

```
<!-- Comment -->
```

Or you can use this (strange) type of comments that has the advantage to be completely removed from the result.

```
[//]: <> (This is also a comment.)
```

## HTML

All the HTML tags are preserved so you can write directly in HTML if needed.

| Markdown                                  | Result                                  |
|:------------------------------------------|:----------------------------------------|
| `1<sup>st</sup>, 2<sup>nd</sup>, ...`     | 1<sup>st</sup>, 2<sup>nd</sup>, &#8230; |
| `<span style="color:red">Red text</span>` | <span style="color:red">Red text</span> |

[Markdown-it](https://github.com/markdown-it/markdown-it) will parse inside "inline" HTML tags, but inside "block" elements the markdown code will be parsed iff the opening tag is followed by a blank line.

| Markdown                                  | Result                                                   |
|:------------------------------------------|:---------------------------------------------------------|
| `<span>**bold** and _italic_</span>`      | <span><b>bold</b> and <em>italic</em></span>             |
| `<div>**bold** and _italic_</div>`        | <div>&#42;&#42;bold&#42;&#42; and &#95;italic&#95;</div> |
| <pre><code>&lt;div><br style="display: inline;"><br style="display: inline;">&#42;&#42;bold&#42;&#42; and &#95;italic&#95;<br style="display: inline;">&lt;/div></code></pre> | <div><b>bold</b> and <em>italic</em></div> |

## Classes and ids

By default Mathconf use the extension [attrs](https://github.com/arve0/markdown-it-attrs) to allow classes and other attributes to be added.

You can add classes, identifiers and attributes to your markdown with `{.class #identifier attr=value attr2="spaced value"}` curly brackets. For example:

```
# Title {.centered #title}
```
produce
```html
<h1 class="centered" id="title">Title</h1>
```

or

```
- First element of list of class `myclass`
- Second element of list of class `myclass`
{.myclass}
```
produce
```html
<ul class="myclass">
  <li>First element of list of class <code>myclass</code></li>
  <li>Second element of list of class <code>myclass</code></li>
</ul>
```

## Escaping the markdown

In some situations it may be useful to avoid parsing a special character or a whole section of code.

### Character escape

We can escape some special characters with `\`, i.e. `\*\*not bold\*\*` will be rendered as `**not bold**`.

The same result can be achieved by replacing a character with its html encoding, ie `&#42;` will be rendered as `*` and not treated as a special asterix character.

### Paragraph escape

To prevent an entire paragraph from being parsed, we can enclose it in `<p>...</p>` (without a blank line after the `<p>`) as explained in the HTML section.

## MathJax

In some situations, MathJax may conflict with Markdown-it. For example, in `$x_i$` the underscore `_` may be interpreted by Markdown-it as the start of italics. In this case we need to escape the whole paragraph or just the underscore.

---
| [<small>👁</small>view source](https://github.com/mathconf/help/blob/master/markdown.md) | [<small>✎</small>edit this page](https://github.com/mathconf/help/edit/master/markdown.md) |
