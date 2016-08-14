.. _ruler:

Line/Area Ruler (Längen und Flächen berechnen)
[55555555555555]
 
Mit dem Lineal wird eine Linie oder eine Fläche gezeichnet, deren Länge oder Flächeninhalt berechnet wird.

.. image:: ../../../../../figures/de/ruler.png
     :scale: 80

Konfiguration
[666666666666]

.. image:: ../../../../../figures/de/ruler_configuration.png
     :scale: 80


* **Title:** Titel des Elements. Dieser wird in der Layouts Liste angezeigt und ermöglicht, mehrere Button-Elemente voneinander zu unterscheiden. Der Titel wird außerdem neben dem Button angezeigt, wenn "Beschriftung anzeigen" aktiviert ist.
* **Tooltip:** Text, der angezeigt wird, wenn der Mauszeiger eine längere Zeit über dem Element verweilt.
* **Target:** ID des Kartenelements, auf das sich das Element bezieht.
* **Type:** Typ des Elements, entweder 'line' oder 'area' (misst nur einzelne Linien oder addiert diese zu einer Fläche).


YAML-Definition:
----

.. code-block:: yaml

   tooltip: "ruler"   # Text des Tooltips
   target: ~          # ID des Kartenelements
   type: 'line'       # Wählen Sie Typ 'line' oder 'area'

Für das Element wird ein Button verwendet. Zu der Konfiguration des Buttons besuchen sie die Dokumentationsseite unter :doc:`button`.

Class, Widget & Style
[66666666666666666666]

* **Class:** Mapbender\\CoreBundle\\Element\\Ruler
* **Widget:** mapbender.element.ruler.js, subclasses mapbender.element.button.js
* **Style:** mapbender.elements.css

HTTP Callbacks
[6666666666666]

Keine.

JavaScript API
[6666666666666]

activate
[7777777]

Aktiviert das Modul, welches auf Mausklicks in der Karte wartet und dann die Messung startet.

deactivate
[777777777]
Deaktiviert das Modul.

JavaScript Signals
[66666666666666666]

Keine.
