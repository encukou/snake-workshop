{% set editor_name = 'Atom' %} {% set editor_url = 'https://atom.io' %} {% extends lesson.slug + '/_base.md' %}

{% block name_gen %} Atom {% endblock %}

{% block setup %}

In Atom, nothing needs to be set up, it works 'out of the box' as it should from production.

Indentation and syntax highlighting will work correctly only in files with the extension `.py` (like Python). In other programming languages, indentation and syntax highlighting are done differently.

Therefore, as soon as you create a new file in this editor, you should save it under the correct name as soon as possible.

{% endblock %}
