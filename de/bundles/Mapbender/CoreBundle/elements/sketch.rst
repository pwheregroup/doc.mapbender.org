.. _sketch:

Sketch
[5555555555555555555555]

Das Skizzen (Sketch) Element fügt einen Vektorlayer in der Karte hinzu, wodurch Geometrieobjekte temporär gezeichnet werden.

.. image:: ../../../../../figures/de/sketch.png
     :scale: 80

Konfiguration
[666666666666666]

.. image:: ../../../../../figures/de/sketch_configuration.png
     :scale: 80

* **Title:** Titel des Elements. Dieser wird in der Layouts Liste angezeigt und ermöglicht, mehrere Button-Elemente voneinander zu unterscheiden. Der Titel wird außerdem neben dem Button angezeigt, wenn “Beschriftung anzeigen” aktiviert ist.
* **Target:** ID des Kartenelements, auf das sich das Element bezieht.
* **Default:** Zeichenart der Skizze (s. Parameter 'types')
* **Types:** Liste der unterstützten Zeichenarten 

YAML-Definition:
----

.. code-block:: yaml

   tooltip: 'Sketch'                # Text des Tooltips
   target: ~                        # ID des Kartenelements
   types: 'circle'                  # Liste der unterstützten Zeichenarten 
   defaultType: 'circle'            # Zeichenart der Skizze (s. Parameter 'types')

Für das Element wird ein Button verwendet. Zu der Konfiguration des Buttons besuchen sie die Dokumentationsseite unter :doc:`button`.

Class, Widget & Style
[666666666666666666666666666]

* **Class:** Mapbender\\CoreBundle\\Element\\Sketch
* **Widget:** mapbender.element.sketch.js

HTTP Callbacks
[66666666666666666666]

Keine.

JavaScript API
[6666666666666]

activate
[7777777]

Aktiviert das Element. Dieses wartet auf einen Mausklick in die Karte, um das Zeichnen zu starten

deactivate
[777777777]

Deaktiviert das Element.

JavaScript Signals
[66666666666666666]

Keine.
