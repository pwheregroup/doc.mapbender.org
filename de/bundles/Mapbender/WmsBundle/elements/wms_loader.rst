.. _wms_loader:

WMS Loader
***********************

Mit diesem Element können WMS per getCapabilities-Request geladen werden.
Es kann WMS 1.1.1 und  WMS 1.3.0 geladen werden.


.. image:: ../../../../../figures/wms_loader.png
     :scale: 80


Konfiguration
=============

.. image:: ../../../../../figures/wms_loader_configuration.png
     :scale: 80

* **Auto open:** true, wenn das Element beim Start der Anwendung geöffnet werden soll, der Standardwert ist false.
* **Split layers:** geteilte Ebenen beim Laden des Dienstes, Standard ist false.
* **Title:** Titel des Elements. Dieser wird in der Layouts Liste angezeigt und ermöglicht, mehrere Button-Elemente voneinander zu unterscheiden. Der Titel wird außerdem neben dem Button angezeigt, wenn “Beschriftung anzeigen” aktiviert ist.
* **Tooltip:** Text, der angezeigt wird, wenn der Mauszeiger eine längere Zeit über dem Element verweilt.
* **Target:** ID des Kartenelements, auf das sich das Element bezieht.
* **Defaultformat:** Standard Format ist image/png, weitere Möglichkeiten: image/gif, image/jpeg.
* **Defaultinfoformat:** Standard Infoformat ist text/html, weitere Möglichkeiten: text/xml, text/plain.

YAML-Definition:
----

.. code-block:: yaml

   target: ~                            # ID des Kartenelements
   tooltip: 'WMS Loader'                # Text des Tooltips
   autoOpen: false                      # true, wenn das Element beim Start der Anwendung geöffnet werden soll, der Standardwert ist false.
   defaultFormat: 'image/png'           # Standard Format ist image/png, weitere Möglichkeiten: image/gif, image/jpeg
   defaultInfoFormat: 'text/html'       # Standard Infoformat ist text/html, weitere Möglichkeiten: text/xml, text/plain
   splitLayers: false                   # geteilte Ebenen beim Laden des Dienstes, Standard ist false

Für das Element wird ein Button verwendet. Siehe unter :ref:`button` für die Konfiguration.
   

Class, Widget & Style
=======================

* **Class:** Mapbender\\WmsBundle\\Element\\WmsLoader
* **Widget:** 
* **Style:** 

HTTP Callbacks
==============

Keine.


JavaScript API
==============

activate
----------

Öffnet einen Dialog, in dem ein WMS über einen getCapabilities-Request geladen werden kann.
Es kann WMS 1.1.1 und  WMS 1.3.0 geladen werden.


JavaScript Signals
==================

Keine.
