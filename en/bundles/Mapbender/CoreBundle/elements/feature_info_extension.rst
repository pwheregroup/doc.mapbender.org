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

* **Load of declarative sources:**  allow to load service from a link (for example from featureInfo or search) and define the layers to activated, default false. 
* **Highlighting of featureinfo hints:** highlight the featureinfo hint of the requested area.
* **Title:** Title of the element in the layout list.
* **Map:** Id of Map element to query.
* **Featureinfo:** feature info element, which is the subject of the extension.


YAML-Definition:
----

.. code-block:: yaml


   tooltip: 'Feature Info Extension'  # text to use as tooltip.
   map: ~                             # Id of Map element.
   featureinfo: ~                     # Id of featureinfo.
   highlight_source: true             # highlight the requested area/ featureinfo hints, default: true 
   load_declarative_wms: true         # allow to load service from a link (for example from featureInfo or search) 
                                      # and define the layers to activated, default false 

You need a feature info-element to show this extension. See the feature_info documentation for inherited configuration options. 


How to highlight the geometry
==============================

You can highlight the featureinfo hint of the requested area. Set **highlight_source** true in mapbender.yml. 

The link has to look like this:

.. code-block:: html

  <div data-geom='MULTIPOLYGON(( [shpxy xf=" " yh=","] ))'>
  <table class="geometryElement" data-geometry="MULTIPOLYGON(...)


.. code-block:: yaml

   highlight_source: true         # highlight the requested area/ featureinfo hints, default: true 



How to add a WMS by defining a link
====================================

You can add a WMS to Mapbender by defining a link f.e. in your WMS featureinfo or your search results.

Set **useDeclarative** true im mapbender.yml or check declarative in administration.

The link has to look like this:

.. code-block:: html

  <a mb-action="source.add.wms" mb-layer-merge="1" mb-wms-merge="1" 
  mb-wms-layers="Gewaesser,Fluesse" 
  href="http://wms.wheregroup.com/cgi-bin/germany.xml?VERSION=1.1.1&REQUEST=GetCapabilities&SERVICE=WMS">load service</a>

  <a mb-action="source.add.wms" mb-layer-merge="1" mb-wms-merge="1" 
  mb-wms-layers="Gewaesser,Fluesse" 
  mb-url="http://wms.wheregroup.com/cgi-bin/germany.xml?VERSION=1.1.1&REQUEST=GetCapabilities&SERVICE=WMS" href="">load service</a>


.. code-block:: yaml

    mb-action="source.add.wms"    # defines action to add a  WMS
    mb-wms-merge="1"              # adds the WMS only once, if WMS is already part of the application it will use the WMS which is there (default is 1)
    mb-layer-merge="1"            # default is 1 which means: activate the layers passed mb-wms-layers and do not disable the layers which are already active.
    mb-wms-layers="Gewaesser,Fluesse" # defines the layers to be activated, _all activates all layers, default all layers are deactivated
    href oder mb-url              # refer to the WMS getcapabilities URL

   

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
