# Textile

[Textile](https://en.wikipedia.org/wiki/Textile_(markup_language)) is a lightweight markup language that uses a text formatting syntax to convert plain text into structured HTML markup.
The [original version](https://textile-lang.com) was written in PHP.
Mathconf.org use the javascript parser [textile.js](https://github.com/borgar/textile-js/).

## Online editor

You can experiment with the textile syntax using the [official playground](http://borgar.github.io/textile-js/).

## Documentation

The syntax is (almost) the same as the original one. So you can read [the original documentation](https://textile-lang.com/doc/).

## Some examples

Here we present some elements of the syntax.

### Paragraphs and titles

| Textile                                   | Result                                                         |
|:------------------------------------------|:---------------------------------------------------------------|
| `h1=. Title (centerd)`                    | <h1 style="text-align:center">Title (centerd)</h1>             |
| `h2=. Subtitle (centerd)`                 | <h2 style="text-align:center">Subtitle (centerd)</h2>          |
| `p=. Paragraph (centerd)`                 | <p style="text-align:center">Paragraph (centerd)</p>           |
| `p<>. Paragraph (justified)`              | <p style="text-align:justify">Paragraph (justified)</p>        |
| `p(blabla). Paragraphe of class "blabla"` | <p class="blabla">Paragraphe of class &#8220;blabla&#8221;</p> |

### Text, links, images

| Textile                            | Result                                                                 |
|:-----------------------------------|:-----------------------------------------------------------------------|
| `*strong*`                         | <strong>strong</strong>                                                |
| `**bold**`                         | <b>bold</b>                                                            |
| `_italic_`                         | <em>italic</em>                                                        |
| `*_combined_*`                     | <strong><em>combined</em></strong>                                     |
| `"INSMI":http://www.cnrs.fr/insmi` | <a href="http://www.cnrs.fr/insmi"><span class="caps">INSMI</span></a> |
| `!https://imgur.com/qzNsLbB.jpg!`  | <img src="https://imgur.com/qzNsLbB.jpg" alt="" />                     |

## Lists

## unordered

| Textile                                                                    | Result                                                                                           |
|:---------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------|
| `* Item A`<br>`** Item A1`<br>`** Item A2`<br>`* Item B`<br>`* Item C`<br> | <ul><li>Item A <ul><li>Item A1</li><li>Item A2</li></ul></li><li>Item B</li><li>Item C</li></ul> |

## Numbered

| Textile                                                                      | Result                                                                                           |
|:-----------------------------------------------------------------------------|:-------------------------------------------------------------------------------------------------|
| `# Item 1`<br>`## Item 1.1`<br>`## Item 1.2`<br>`# Item 2`<br>`# Item 3`<br> | <ol><li>Item A <ol><li>Item A1</li><li>Item A2</li></ol></li><li>Item B</li><li>Item C</li></ol> |

## Comments

Every paragraph that starts with `###.` is removed from the final output.

```textile
###. An invisible comment !
And the following line is also invisible because it is part of the same paragraph.

But this paragraph is visible (because there is an empty line between the two)
```
## HTML

All the HTML tags are preserved so you can write directly in HTML if needed.

| Textile                                   | Result                                  |
|:------------------------------------------|:----------------------------------------|
| `1<sup>st</sup>, 2<sup>nd</sup>, ...`     | 1<sup>st</sup>, 2<sup>nd</sup>, &#8230; |
| `<span style="color:red">Red text</span>` | <span style="color:red">Red text</span> |

## Classes, styles and ids

To be style some element using CSS it can be useful to add the following attributes.

### class and ids

CSS classes and IDs are enclosed in parentheses `()` just after phrase modifiers or block modifiers.
For example:

```textile
p(myclass#myid). This paragraph has both a `class` and an `id`.
```
produce
```html
<p class="myclass" id="myid">This paragraph has both a `class` and an `id`.</p>
```

or

```textile
*(myclass) First element of list of class `myclass`
* Second element of list of class `myclass`
```
produce
```html
<ul class="myclass">
  <li>First element of list of class `myclass`</li>
  <li>Second element of list of class `myclass`</li>
</ul>
```

### style

It is preferable to use classes to style your elements, but if it is needed you can directly apply a style like this

```textile
%{color:red}Text in red%
```

that produce <span style="color:red">Text in red</span> (`<span style="color:red">Text in red</span>`).

---
| [<small>👁</small>view source](https://github.com/mathconf/help/blob/master/textile.md) | [<small>✎</small>edit this page](https://github.com/mathconf/help/edit/master/textile.md) |
