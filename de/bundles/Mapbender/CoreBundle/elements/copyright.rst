.. _copyright:

Copyright
[55555555555]

Dieses Element zeigt die Nutzungsbedingungen ("Terms of use") in einem Dialog an.

.. image:: ../../../../../figures/de/copyright.png
     :scale: 80

Konfiguration
[666666666666]

.. image:: ../../../../../figures/de/copyright_configuration.png
     :scale: 80

* **Automatisches Öffnen (Autoopen):** Schaltet ein/aus, ob das Copyright Fenster beim Start der Anwendung automatisch geöffnet werden soll (Standard: Ausgeschaltet).
* **Title:** Titel des Elements. Der Titel wird neben dem Button angezeigt.
* **Tooltip:** Text, der als Tooltip angezeigt wird. Dieser wird angezeigt, wenn der Mauszeiger längere Zeit über dem Button verweilt. Er wird außerdem als Kopfzeile im Copyright Fenster verwendet.
* **Content:** Inhalt des Copyright Fensters. Dieser wird angezeigt, wenn das Element per Click aktiviert wird (oder bei Start der Anwendung wenn die "automatisches Öffnen" Option aktiviert wurde).

YAML-Definition:
----

.. code-block:: yaml

   class: Mapbender\CoreBundle\Element\Copyright
   title: "Copyright"              # Titel des Elements
   tooltip: "Copyright"            # Text des Tooltips
   content: "Lorem ipsum"          # Erstellen Sie ihren Text für das Copyright
   autoOpen: true                  # Automatisches Öffnen beim Start der Anwendung
                

Class, Widget & Style
[666666666666666666666]

* **Class:** Mapbender\\CoreBundle\\Element\\Copyright
* **Widget:** mapbender.element.copyright.js
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
