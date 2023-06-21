{% extends lesson.slug + '/_base.md' %}

{% block install %}

On Linux, {{ editor_name }} is installed like any other program.

Fedora
:   ```console
    $ sudo dnf install {{ editor_cmd }}
    ```


Ubuntu: 
:   ```console
    $ sudo apt-get install {{ editor_cmd }}
    ```

If you use a different Linux, I assume that you know how to install programs. :)

For Windows and macOS, {{ editor_name }} can be downloaded from the [homepage]({{ editor_url }}).

{% endblock %}
