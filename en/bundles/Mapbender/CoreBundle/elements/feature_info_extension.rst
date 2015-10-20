.. _feature_info_extension:

Feature Info Extension
***********************

This element provides an extension for the feature info capabilities to Mapbender3. It works for WMS services.
The extension allows color highlighting a requested area by moving the mouse to the previously defined area.

Starting the info query via a mouse click on the map to open the dialog box. The requested area is now highlighted in yellow on the map. The area is highlighted in dark blue with a dark border when the cursor is on the defined area.

.. image:: ../../../../../figures/feature_info_extension.png
     :scale: 80

Configuration
=============

.. image:: ../../../../../figures/feature_info_extension_configuration.png
     :scale: 80

Needed for the configuration of the extension is the feature info element. More on this topic can be found at http://doc.mapbender3.org/en/bundles/Mapbender/CoreBundle/elements/feature_info.html

* **Load of declarative sources:**
* **Highlighting of featureinfo hints:** 
* **Title:** Title of the element in the layout list.
* **Map:** Id of Map element to query.
* **Featureinfo:** feature info element, which is the subject of the extension.


YAML-Definition:
----

.. code-block:: yaml


   tooltip: 'Feature Info Extension'  # text to use as tooltip.
   map: ~	                          # Id of Map element.
   featureinfo: ~	                  # Id of featureinfo.
   highlight_source: true             # highlight the requested area/ featureinfo hints, default: true 
   load_declarative_wms: true         # to load the declarative sources, default: true 


You need a feature info-element to show this extension. See :doc:`feature_info` for inherited configuration options. 

Class, Widget & Style
============================

* **Class:** Mapbender\\CoreBundle\\Element\\FeatureInfoExt
* **Widget:** mapbender.element.featureInfoext.js
* **Style:** mapbender.elements.css

HTTP Callbacks
==============

None.

JavaScript API
==============

activate
--------

Activates the widget which then waits for mouse click on the map and starts the feature info extension.

deactivate
----------
Deactivates the widget.

JavaScript Signals
==================

None.
