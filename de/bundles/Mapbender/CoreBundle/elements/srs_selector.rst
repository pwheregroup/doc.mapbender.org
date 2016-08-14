.. _srs_selector:

Spatial Reference System Selector (SRS Selector) (Auswahl des räumlichen Referenzsystems)
[55555555555555555555555555555555555555555555555555555555555555555555555555555555555555555555555]

Nach der Auswahl eines räumlichen Referenzsystems (SRS) ändert sich das räumliche Referenzsystem in der Karte.
Beachten Sie: Die Selektbox bietet nur die SRS an, die für das `Kartenelement <../elements/map.html>`_ definiert wurden.


.. image:: ../../../../../figures/de/srs_selector.png
     :scale: 100

Konfiguration
[666666666666]

.. image:: ../../../../../figures/de/srs_selector_configuration.png
     :scale: 80

* **Title:** Titel des Elements. Dieser wird in der Layouts Liste angezeigt und ermöglicht, mehrere Button-Elemente voneinander zu unterscheiden. Der Titel wird außerdem neben dem Button angezeigt, wenn "Beschriftung anzeigen" aktiviert ist.
* **Tooltip:** Text, der angezeigt wird, wenn der Mauszeiger eine längere Zeit über dem Element verweilt. 
* **Target:** ID des Kartenelements, auf das sich das Element bezieht.

YAML-Definition:
----

.. code-block:: yaml

   tooltip: 'SRS Selector'  # Text des Tooltips
   label: false             # false/true, um die SRS Auswahl zu beschriften. Der Standardwert ist false.
   target: ~                # ID des Kartenelements
   
Class, Widget & Style
[66666666666666666666]

* **Class:** Mapbender\\CoreBundle\\Element\\SrsSelector
* **Widget:** mapbender.element.srsselector.js
* **Style:** mapbender.elements.css

HTTP Callbacks
[6666666666666]

Keine.

JavaScript API
[6666666666666]

showHidde
[77777777]
<>

selectSrs
[777777777]
<>

getSelectedSrs
[777777777777777]
<>

isSrsSupported
[777777777777777]
<>

isSrsEnabled
[777777777777777]
<>

disableSrs
[777777777777777]
<>

enableSrs
[777777777777777]
<>

enableOnlySrs
[777777777777777]
<>

getFullSrsObj
[777777777777777]
<>

enableAllSrs
[77777777777777]
<>

disableAllSrs
[777777777777777]
<>

getInnerJoinSrs
[777777777777777]
<>

getInnerJoinArrays
[777777777777777777777]
<>

JavaScript Signals
[66666666666666666]

Keine.
