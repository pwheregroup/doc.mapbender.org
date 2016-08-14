.. _wmc_editor:

WMC Editor
[5555555555555555555555]

Im Mapbender können mit dem WMC Editor Konfigurationen gespeichert und bearbeitet werden. 
Diese Konfigurations können mit dem WMC-Lader geladen werden. Mehr dazu unter `WMC Loader <../elements/wmc_loader.html>`_.

Sie können den WMC-Editor ihrer Applikation hinzufügen. Beachten Sie, dass der WMC-Editor einen Button benötigt.

Mit dem Editor können Konfigurationen erzeugt und bearbeitet werden. Es können Konfigurationen mit einem Titel, einer Beschreibung und einem Screenshot gespeichert werden.



.. image:: ../../../../../figures/wmc_editor.png
     :scale: 80

.. image:: ../../../../../figures/wmc_editor_2.png
     :scale: 80


Konfiguration
[666666666666]

.. image:: ../../../../../figures/wmc_editor_configuration.png
     :scale: 80

* **Title:** Titel des Elements. Dieser wird in der Layouts Liste angezeigt und ermöglicht, mehrere Button-Elemente voneinander zu unterscheiden. Der Titel wird außerdem neben dem Button angezeigt, wenn “Beschriftung anzeigen” aktiviert ist.
* **Tooltip:** Text, der angezeigt wird, wenn der Mauszeiger eine längere Zeit über dem Element verweilt.
* **Target:** ID des Kartenelements, auf das sich das Element bezieht.
* **Accessgroups:** definiert Gruppen, die den WMC Editor verwenden können.

YAML-Definition:
----

.. code-block:: yaml

    title: WMC Editor
    tooltip: WMC Editor   # Text des Tooltips
    target: map           # Name des Kartenelements 
    accessGroups: [0,1]   # definiert Gruppen, die den WMC Editor verwenden können

Für das Element wird ein Button benötigt. Siehe unter :ref:`button_de` für die Konfiguration.

Class, Widget & Style
[6666666666666]

* **Class:** Mapbender\\WmcBundle\\Element\\WmcEditor
* **Widget:** <Put Widget name here>
* **Style:** <Put name of css file here>


HTTP Callbacks
[6666666666666]


<action>
[7777777777777777777777777777777]

Öffnet einen Dialog mit einem Editor, in dem Konfigurationen gespeichert und bearbeitet werden können.


JavaScript API
[6666666666666]


<function>
[777777777]


JavaScript Signals
[66666666666666666]

<signal>
[7777777]


