
{% set editor_name = 'Gedit' %} {% set editor_cmd = 'gedit' %} {% set editor_url = 'https://wiki.gnome.org/Apps/Gedit' %} {% extends lesson.slug + '/_linux_base.md' %}

{% block name_gen %} Gedit {% endblock %}

{% block setup %}

Gedit is configured in Preferences.

{{ figure(img=static('gedit_prefs.png'), alt="") }}

Line numbering: In the View section, select Display Line Numbers.

{{ figure(img=static('gedit_linenums.png'), alt="") }}

Indentation: In the Editor section, select:

* Tab width: 4
* Insert spaces instead of tabs
* Enable automatic indentation

{{ figure(img=static('gedit_indent.png'), alt="") }}

Syntax Highlighting works automatically, but the coloring method is selected based on the file extension - for example, `.py` for Python.

Therefore, as soon as you create a new file in this editor, you should save it under the correct name as soon as possible.

{% endblock %}
