{% set editor_name = 'Notepad++' %} {% set editor_url = 'https://notepad-plus-plus.org/' %} {% extends lesson.slug + '/_base.md' %}

{% block name_gen %} Notepad++ {% endblock %}

{% block install %}

Notepad++ is only available for Windows.

Download it from its [homepage](https://notepad-plus-plus.org/) and install it.

{% endblock %}

{% block setup %}

Indentation: In the Settings menu, choose Options, then Syntax, and then set "Tab Settings" to "Replace by Space".

The syntax highlighting will work automatically in files with the extension `.py` (like Python). In other programming languages, indenting and syntax highlighting works differently.

Therefore, as soon as you create a new file in this editor, you should save it under the correct name as soon as possible.

{% endblock %}
