Configure your WMS via the Mapbender3 Service Instance interface
================================================================================
You can configure the WMS for your specific application. This is a useful step if you want (for example):

* hide a specific layer from the map,
* change the order or title of your layers,
* want to provide FeatureInfo - request only for specific layers,
* change the scale visibility of your layers.

#. Choose ``Applications -->`` |mapbender3-button-edit| ``edit-Button --> Layers --> edit-Button`` to edit the Service Instance.

#. At the top of the interface, you can set general information about your Service. For further clarification, please look up the chapter Service configuration.

#. Beneath, you will see a table with the layers of the Service. 

#. Moreover, you can change the order of the layers quickly via drag & drop.

.. image:: ../../../../../figures/mapbender3_wms_application_settings.png
  :scale: 80

**Service configuration:**

* Title: Service name shown in the application.
* Format: Choose the format for getMap-Requests. Default is "image/PNG".
* Infoformat: Choose the format for getFeatureInfo-Requests.
* Exceptionformat: Choose the format for exceptions.
* Opacity: Choose opacity in percent. 0 results in a completely transparent Service.
* Tile buffer: This parameter is valid for tile services and specifies if additional tiles should be requested. If the user pans the map, these tiles will be already downloaded and visible. The higher the value, the more tiles are requested. Default: 0.
* BBOX-Faktor: This parameter is valid for non-tiled WMS services. You can specify the size of the returned map-image. A value greater than 1 will request a bigger map-image. Default: 1.25, can be set to 1.
* Visible: Set the visibility of the request. 
* BaseSource: Specifies if the Service should be handled as a BaseSource (BaseSources can be shown/hidden in the layertree).
* Proxy: If active, the service will be requested by Mapbender and not directly.
* Transparency: Default is active, the source is without a transparent background if it is deactivated (getMap-Request with TRANSPARENT=FALSE).
* Tiled: You can request a WMS in tiles, default is not tiled. This may be a good choice if you map is very big an the WMS service does not support the width/height.


**Vendor Specific Parameter:**

You can define Vendor Specific Parameters in a layerset instance to add them
to a WMS request. This principle follows Multi-Dimensions in the WMS
specification.

You can use Vendor Specific Parameters in Mapbender3 for example to add the
user- and group information of the logged-in user to a WMS request. You can
also add hard coded values.

The following example shows the definition of the parameter "group" which
transfers the group-value of the logged-in user.

.. image:: ../../../../../figures/mapbender3_vendor_specific_parameter.png
           :scale: 80
      


* Type: „single“, „multiple“, „interval“ (multiple values in dimensions)
* Name: parameter name of the WMS request.
* Default: the default value.
* Extent: available values (multiple as a comma seperated list).
* Vstype: Mapbender3 specific variables. Group (groups), User (users), Simple.
* Hidden: If this value is set, requests are send via a server so that the parameters are not directly visible.

Currently, the element can be used to transfer user- and groupinformation,
e.g. for a user the $id$ and for groups the value $group$.

**Layer Configuration:**

The layer table offers several checkboxes and two scale visibility fields that adjust the functionality of your Service Instance. Please note that the checkbox on top changes all the layer instances for the respective configuration at once.

* Title: Layer title from Service information shown in Mapbender3, adjustable.
* Active (on/off): Enables/disables a layer for the individual application layer. If not set, all other checkboxes of the same layer will be ignored.
* Select on: Selectable in geodata explorer.
* Select allow: Layer is active when the application starts.
* Info on: Layer provides feature info requests, info default activates the feature info functionality.
* Info allow: layer info is active when the application starts.
* Minscale / maxscale: the scale range in which the layer should be displayed, 0 or no entry = no scale limitation.
* Toggle: Opens the folder on start of the application.
* Reorder: Allows to reorder the layers with drag & drop while using the application.

* ... -> Opens a dialog with more information:
* Layer's name: Layer name of the service information (for getMap-Requests, not adjustable).
* Style: If a WMS provides more than one style, you can choose a different style than the default style.
