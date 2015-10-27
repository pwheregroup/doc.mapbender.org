.. _wms_loader:

WMS Loader
***********************

Opens a dialog in  which a WMS can be loaded via the getCapabilities-Request.
You can load WMS 1.1.1 and  WMS 1.3.0.


.. image:: ../../../../../figures/wms_loader.png
     :scale: 80


Configuration
=============

.. image:: ../../../../../figures/wms_loader_configuration.png
     :scale: 80

* **Auto open:** true/false open when application is started, default false.
* **Split layers:** split layer on load of the service, default false.
* **Title:** Title of the element. The title will be listed in "Layouts" and allows to distinguish between different buttons. It will be indicated if "Show label" is activated.
* **Tooltip:** text to use as tooltip.
* **Target:** Id of Map element to query.
* **Defaultformat:** default format is image/png, further possibilities: image/gif, image/jpeg.
* **Default infoformat:** default infoformat is text/html, further possibilities: text/xml, text/plain.

YAML-Definition:
----

.. code-block:: yaml

   target: ~                            # Id of Map element to query
   tooltip: 'WMS Loader'                # text to use as tooltip
   autoOpen: false                      # true/false open when application is started, default false 
   defaultFormat: 'image/png'           # default format is image/png, further possibilities: image/gif, image/jpeg
   defaultInfoFormat: 'text/html'       # default infoformat is text/html, further possibilities: text/xml, text/plain
   splitLayers: false                   # split layer on load of the service, default false

You need a button to show this element. See :ref:`button_en` for inherited configuration options.


Class, Widget & Style
=======================

* **Class:** Mapbender\\WmsBundle\\Element\\WmsLoader
* **Widget:** 
* **Style:** 

HTTP Callbacks
==============

None.


JavaScript API
==============

activate
----------

Opens a dialog in wich a WMS can be loaded via the getCapabilities-Request.
You can load WMS 1.1.1 and WMS 1.3.0.


JavaScript Signals
==================

None.
