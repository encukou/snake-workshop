{% set editor_name = 'Visual Studio Code' %}
{% set editor_url = 'https://code.visualstudio.com' %}
{% extends lesson.slug + '/_base.md' %}

{% block name_gen %}Visual Studio Code{% endblock %}

{% block install %}

## Download and installation

You can download the editor from its [homepage](https://code.visualstudio.com/).
Choose the green Download button and select the installer for your system.
Then follow the installer instructions as with any other program.

### Sending telemetry data

This text editor, however, sends data about your usage ([most likely including, for example, the content of open files][privacy]).
If you do not wish for the data to be sent, you can cancel the sending.

Open **File** > **Preferences** > **Settings** (macOS: **Code** > **Preferences** > **Settings**).
Find `telemetry.enableTelemetry` and uncheck this entry.

Also see the [original English guide](https://code.visualstudio.com/docs/supporting/faq#_how-to-disable-telemetry-reporting).

[privacy]: https://privacy.microsoft.com/en-us/privacystatement

{% endblock %}
{% block setup %}

Everything else is already installed. It's time to start programming!

{% endblock %}
