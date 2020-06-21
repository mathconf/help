# Topics

## Pages

Every page has some parameters :

- **URL**: the pages with the same url (for example `home`) written in different languages (for example `fr` and `en`) are corresponding to each other.
- **Publish**: if not checked the page is not visible on the conference site.
- **Language**: the language of the page. If you want to create a new language version of a page you can simply change this field and save it, after that you can simply translate the content of this new page.
- **Menu title**: is the corresponding text that in the menu. If you want to indent the menu item you can add `&nbsp;` (which is the HTML code of a non-breaking space).
- **Weight**: is used to sort the menu items.
- **Format**: determine if the content is edited in `textile` or in `markdown`.

### Textile

[Textile](https://en.wikipedia.org/wiki/Textile_(markup_language)) is a lightweight markup language that uses a text formatting syntax to convert plain text into structured HTML markup.

For example to write something in **bold** you can simply type `**bold**`. And the link to [MathConf](https://www.mathconf.org) is produced by `"MathConf":https://www.mathconf.org`.

For more information on **textile** visit the [dedicated page](textile.md).

### Markdown

[Markdown](https://en.wikipedia.org/wiki/Markdown) like textile is a lightweight markup language. The two languages are very similar but has also somme differences. Markdown is far more popular than textile.

For example to write something in **bold** you can simply type `**bold**`, like in textile. But to produce the link to [MathConf](https://www.mathconf.org) the syntax is different: `[MathConf](https://www.mathconf.org)`.

For more information on **markdown** visit the [dedicated page](markdown.md).

## Forms

The forms on MathConf are described in three steps:

- The form itself is described in [YAML](https://en.wikipedia.org/wiki/YAML) a human-readable data-serialization language.
- The confirmation on the screen that is displayed after the form is submited.
- The confirmation mail that is send to the subscriber (and optionally to the organizers).

For more information on how to edit a **form** visit the [dedicated page](forms.md).

## Answers

Here you can manage the form answers. In general there is only one form, the registration form, and here you can manage (consult, edit, export) the list of participants.

## Parameters

In this section you configure all general settings about your conference site:

## Files

The files are *low level plumbing*. In general you don't need to touch this section, but if you are interested how it works you can visit the [dedicated page](files.md).
