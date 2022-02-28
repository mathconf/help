# Forms

## The YAML description

[YAML](https://en.wikipedia.org/wiki/YAML) is a human-readable data-serialization language that is used in www.mathconf.org to describe the fields in a form as in the following examples.

### Form name

- YAML code

    ```yaml
    - type: formname
      lable: "Formulaire d'inscription"
    ```

- HTML result

    ```html
    <legend>Formulaire d'inscription</legend>
    ```
### Text message

- YAML code

    ```yaml
    - type: message
      html: Formulaire pour la participation <b>en ligne</b> seulement.
      class: alert alert-success
    ```

- HTML result

    ```html
    <div class="alert alert-success">Formulaire pour la participation <b>en ligne</b> seulement.</div>
    ```


### Single line text field

- YAML code

    ```yaml
    - type: text
      lable: "Prénom"
      name: firstname
      required: yes
      public: yes
      filter: title
      help: "Votre prénom"
    ```

- HTML result

    ```html
    <label class="labtitle labrequired" for="firstname">Prénom</label>
    <label class="labhelp" for="firstname">Votre prénom</label>
    <input id="firstname" name="firstname" class="required">
    ```

### Email field

- YAML code

    ```yaml
    - type: email
      lable: "Email"
      name: email
      required: yes
      help: "Votre adresse éléctronique"
    ```

- HTML result

    ```html
    <label class="labtitle labrequired" for="email">Email</label>
    <label class="labhelp" for="email">Votre adresse éléctronique</label>
    <input id="email" name="email" class="required email">
    ```

### Date field

- YAML code

    ```yaml
    - type: date
      lable: "Date d'arrivée"
      name: arrival
      required: yes
      default: 2012-7-8
      min: 2012-7-8
      max: 2012-7-28
      help: >-
        Les deux premières semaines (9-21 juillet)
        seront consacrées à des cours avancés,
        la troisième (23-28 juillet) à un mini colloque.
    ```

- HTML result

    ```html
    <label class="labtitle labrequired" for="arrival">Date d'arrivée</label>
    <label class="labhelp" for="arrival">Les deux premières semaines (9-21 juillet)
    seront consacrées à des cours avancés,
    la troisième (23-28 juillet) à un mini colloque.</label>
    <input id="arrival" name="arrival" class="required date" first="2012-7-8" last="2012-7-28" default="2012-7-8">
    ```

### Select field

- YAML code

    ```yaml
    - type: select
      lable: "Voulez-vous donner un exposée"
      name: exposee
      options:
      - value: 1
        lable: Oui
        selected: yes
      - value: 0
        lable: Non
    ```

- HTML result

    ```html
    <label class="labtitle " for="exposee">Voulez-vous donner un exposée</label>
    <select id="exposee" name="exposee">
        <option value="1" selected="selected">Oui</option>
        <option value="0">Non</option>
    </select>
    ```

### Multiline text field

- YAML code

    ```yaml
    - type: textarea
      lable: "Autres remarques"
      name: remarks
      help: >-
        Si vous avez des besoins particuliers
        (régime alimentaire, allergies, végétarien, ...)
        dite-nous, s'il vous plaît.
    ```

- HTML result

    ```html
    <label class="labtitle " for="remarks">Autres remarques</label>
    <label class="labhelp" for="remarks">Si vous avez des besoins particuliers
    (régime alimentaire, allergies, végétarien, ...)
    dite-nous, s'il vous plaît.</label>
    <textarea id="remarks" name="remarks"></textarea>
    ```

### Submit button

- YAML code

    ```yaml
    - type: submit
      lable: "S'enregistrer"
      class: "btn btn-success"
    ```

- HTML result

    ```html
    <input type="submit" value="S'enregistrer" class="submit btn btn-success">
    ```

### CSS classes

You can add to any field the `class:` key like in the sumit button exmple.

### Multiline strings in YAML

From time to time we need to write multiline strings in the `help` or in the `html` parts. You can check [yaml-multiline.info](https://yaml-multiline.info/) for more information on how to do this.


## The responses

You can edit the on screen response and the email response. The message can be edited in [textile](textile.md) or in [markdown](markdown.md) and you can use the form results that are accessibla trough the `answer` variable.

For example to display the firstname in bold you can use:
<!-- {% raw %} -->
```
**{{ answer.firstname }}**
```
<!-- {% endraw %} -->
You can also use all [jinja2](http://jinja.pocoo.org/docs/) filters. For example, to capitalize the familyname:
<!-- {% raw %} -->
```
 {{ answer.familyname | upper }}
```
<!-- {% endraw %} -->
The full list of filters is [available here](https://jinja.palletsprojects.com/en/3.0.x/templates/#list-of-builtin-filters). And you can check your answer template with the [Jinja2 live parser](http://jinja.quantprogramming.com/).

There is an additional variable <!-- {% raw %} -->`{{editanswer}}`<!-- {% endraw %} --> that allows you to obtain the url for editing the submited answer.

---
| [<small>👁</small>view source](https://github.com/mathconf/help/blob/master/forms.md) | [<small>✎</small>edit this page](https://github.com/mathconf/help/edit/master/forms.md) |
