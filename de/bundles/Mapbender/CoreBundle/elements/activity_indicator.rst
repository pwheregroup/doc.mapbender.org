.. _activity_indicator:

Activity Indicator (Aktivitätsindikator)
[55555555555555555555555555555555555555555555555555555]

Der Aktivitätsindikator (Sanduhr) ist ein einfaches Modul, das Aktivitäten anzeigt (Ajax-Aufrufe und Kartenaufrufe). In der voreingestellten Konfiguration wird ein Schrift-Symbol verwendet. Dieses kann ganz einfach in der css-Datei ``fom//src//FOM//CoreBundle//Resources//public//css/frontend//mapbender3_theme.css`` geändert werden.

.. image:: ../../../../../figures/activity_indicator.png
     :scale: 100

Konfiguration
[666666666666]

.. image:: ../../../../../figures/de/activity_indicator_configuration.png
     :scale: 80

* **Title:** Titel des Elements
* **Tooltip:** Der hier eingegebene Text wird angezeigt, wenn der Mauszeiger längere Zeit über dem Element verweilt.
* **Activity class:** CSS Klasse, die Aktivitäten anzeigt (Ajax oder Kacheln)
* **Ajax activity class:** CSS Klasse, die Ajax-Aktivitäten anzeigt
* **Tile activiy class:** CSS Klasse, die Kartenaufrufe anzeigt


YAML-Definition:
----

.. code-block:: yaml

    activityClass: mb-activity          # CSS Klasse, die Aktivitäten anzeigt (Ajax oder Kacheln)
    ajaxActivityClass: mb-activity-ajax # CSS Klasse, die Ajax-Aktivitäten anzeigt
    tileActivityClass: mb-activity-tile # CSS Klasse, die Kartenaufrufe anzeigt

Class, Widget & Style
[666666666666666666666666666]

* **Class:** Mapbender\\CoreBundle\\Element\\ActivityIndicator
* **Widget:** mapbender.element.activityindicator.js
* **Style:** mapbender.elements.css

HTTP Callbacks
[6666666666666]

Keine.

JavaScript API
[6666666666666]

Keine.

JavaScript Signals
[66666666666666666]

Keine.
