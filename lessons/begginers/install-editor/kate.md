{% set editor_name = 'Kate' %} {% set editor_cmd = 'kate' %} {% set editor_url = 'https://kate-editor.org/get-it/' %} {% extends lesson.slug + '/_linux_base.md' %}

{% block name_gen %} Kate {% endblock %}

{% block setup %}

Line numbering: In the View menu, select Show Line Numbers.

Indentation: In the Settings menu, select Configure Kate.

There in Editing select Indentation, set there:

* Default indentation mode: Python
* Indent using: Spaces
* Tab Width: 4 characters
* Indentation width: 4 characters
* Backspace key in leading blank space unindents

Syntax highlighting works automatically, but the way of coloring is chosen based on the file extension - for example, `.py` for Python.

Therefore, as soon as you create a new file in this editor, you should save it under the correct name as soon as possible.

{% endblock %}
