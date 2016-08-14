.. _about_dialog:

About Dialog (Über-Dialog)
[5555555555555555555555555555555]

Dieses Element rendert einen `Button <../elements/button.html>`_, der einen Dialog mit der aktuellen Mapbender Version anzeigt. Der Button kann im Standard-Tempalte wie gehabt in der Toolbar verwendet werden oder auch in die Footer Region positioniert werden.

.. image:: ../../../../../figures/de/about_dialog.png
     :scale: 80

Konfiguration
[666666666666]

.. image:: ../../../../../figures/de/about_dialog_configuration.png
     :scale: 80

* **Beschriftung anzeigen (Show label):** Schaltet Text neben dem About Dialog Button ein/aus.
* **Title:** Text, der neben dem About Dialog Button angezeigt wird.
* **Tooltip:** Text, der erscheint wenn der Mauszeiger längere Zeit über dem Button gehalten wird. 



YAML-Definition:
[777777777777777]

.. code-block:: yaml

   title: 'Über Mapbender3'     # Text, der neben dem About Dialog Button angezeigt wird
   tooltip: 'Über Mapbender3'   # Text des Tooltips
   label: true                  # false/true, um den Button zu beschriften. Der Standardwert ist true.
   icon: 'abouticon'            # Symbol für den Button

   
Class, Widget & Style
[666666666666666666666]

* **Class:** Mapbender\\CoreBundle\\Element\\AboutDialog
* **Widget:** mapbender.mbAboutDialog
* **Style:** mapbender.elements.css

HTTP Callbacks
[6666666666666]

about
[7777]

Ruft Inhalte des Dialogs auf.

JavaScript API
[6666666666666]

Keine.

JavaScript Signals
[66666666666666666]

Keine.

