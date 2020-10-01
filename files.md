# Files

Every file named `name.ext` is served on the address `www.mathconf.org/urlconf/file/name.ext`  where `urlconf` is the url of your conference.

## CSS and JS files

The `.css` and the `.js` files are ordered by name and inserted in the conference site (more precisely in the head of `main.html`) after the default `.css` files. So you can modify even existing styles and add additional dynamic behaviors.

To change the style of a page you can use the classes that are automatically added to `div#main` as `type-page` for the pages, `type-form` for the forms, `type-formanswers` for the page with answers, `lang-fr` for French pages (and for all other languages) and `url-home` for the page or form with `home` as url.

Thus for example to make red the `h1` titles of all the pages in French it is enough to put in a `.css` file the following code:
```css
div#main.type-page.lang-fr h1{
  color: red;
}
```

## Special files

### Insertion files

Not only the `.css` and `.js` files are inserted in `main.html`. The `html` files `head.inc`, `body_prepend.inc` and `body_append.inc` allow to add code in the `<head>` and `<body>` sections (at the beginning and at the end) respectively, of the `main.html`, without touching it. For example, if you found a suitable font (say `Sonsie One`) for the title at [Google fonts](https://fonts.google.com/specimen/Sonsie+One), you can:

- create a file `head.inc` and put inside:

    ```html
    <link href='http://fonts.googleapis.com/css?family=Sonsie+One' rel='stylesheet' type='text/css'>
    ```

- create a file `custom.css` and put inside:

    ```css
    div.header .title {
      font-family: 'Sonsie One', cursive;
    }
    ```

### Replacement files

If you want a more drastic intervention you can replace the default files `main.css`, `main.html` or `main.js`, just by creating a file with this name (and check the "Use this file" box). At the creation of this files, the original content is copied, so you can modify it and use it as replacement.

### regex.json

The file `regex.json` is a `json` file of replacement rules used to create "snippets". For more information you can visit the [dedicated page](https://mathconf.github.io/regex/).

---
| [<small>👁</small>view source](https://github.com/mathconf/help/blob/master/files.md) | [<small>✎</small>edit this page](https://github.com/mathconf/help/edit/master/files.md) |
