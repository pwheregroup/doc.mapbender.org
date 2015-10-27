.. _feature_info_extension:

Feature Info Erweiterung 
***********************

Dieses Element stellt eine Erweiterung für die Infoabfrage bereit, die mit WMS Services funktioniert.
Die Erweiterung ermöglicht eine farbliche Hervorhebung einer abgefragten Geometrie durch das Bewegen des Mauszeigers auf die vorher definierte Fläche. 

Durch das Starten der Infoabfrage über einen Mausklick auf der Karte öffnet sich das Dialogfenster und die abgefragte Fläche wird auf der Karte gelb markiert. Wenn nun der Mauszeiger auf die markierte Fläche kommt, so färbt sich diese dunkelblau und wird hervorgehoben. 

.. image:: ../../../../../figures/de/feature_info_extension.png
     :scale: 80

Konfiguration
=============

.. image:: ../../../../../figures/de/feature_info_extension_configuration.png
     :scale: 80

Für die Konfiguration der Erweiterung ist das FeatureInfo-Element die Vorraussetzung. Mehr zu diesem Thema finden Sie unter http://doc.mapbender3.org/de/bundles/Mapbender/CoreBundle/elements/feature_info.html

* **Laden von delarativen Quellen:** erlaubt einen Dienst über einen Link zu laden (zum Beispiel über die Informationsabfrage oder Suche) und definiert die Layer zu aktivieren, Standard ist false.
* **Hervorheben von FeatureInfo Treffern:** Farbliches Hervorheben der Treffer auf dem Kartenausschnitt bei einer Informationsabfrage.
* **Title:** Titel des Elements. Dieser wird in der Layouts Liste angezeigt und ermöglicht, mehrere Elemente voneinander zu unterscheiden.
* **Map:** ID des Kartenelements, auf das sich das Element bezieht.
* **Featureinfo:** FeatureInfo-Element, auf das sich die Erweiterung bezieht. 


YAML-Definition:
----

.. code-block:: yaml

   tooltip: 'Feature Info Extension'  # Text des Tooltips.
   map: ~                             # ID des Kartenelements.
   featureinfo: ~                     # ID des FeatureInfo-Elements.
   highlight_source: true             # aktiviert die farblich Hervorhebung der Treffer. Standardwert ist true. 
   load_declarative_wms: true         # erlaubt einen Dienst über einen Link zu laden (zum Beispiel über die Informationsabfrage oder Suche) und definiert die Layer zu aktivieren, Standard ist true.

Für das Element wird das FeatureInfo-Element benötigt. Zu der Konfiguration der Infoabfrage besuchen sie die Dokumentationsseite unter Feature Info.


Hervorheben von Geometrien
===========================

Sie können die Treffer auf dem Kartenausschnitt farblich hervorheben. Beim Mouse-Over auf ein Ergebnis wird die ausgewählte Geometrie in einer anderen Farben hervorgehoben. Setzen Sie **highlight_source** auf true in der mapbender.yml. 

Der Link sollte folgendermaßen aussehen:

.. code-block:: html

  <div data-geom='MULTIPOLYGON(( [shpxy xf=" " yh=","] ))'>
  <table class="geometryElement" data-geometry="MULTIPOLYGON(...)


.. code-block:: yaml

   highlight_source: true         # aktiviert die farblich Hervorhebung der Treffer. Standardwert ist true.  



Hinzufügen eines WMS über einen definierten Link
===================================================

Mapbender kann ein WMS über einen definierten Link hinzugefügt werden, z.B. zum Beispiel über die Informationsabfrage oder über Suchergebnisse.

Stellen Sie **useDeclarative** in der mapbender.yml auf true oder stellen Sie in diesem Element auf **useDeclarative**

Der Link sollte folgendermaßen aussehen:

.. code-block:: html

  <a mb-action="source.add.wms" mb-layer-merge="1" mb-wms-merge="1" 
  mb-wms-layers="Gewaesser,Fluesse" 
  href="http://wms.wheregroup.com/cgi-bin/germany.xml?VERSION=1.1.1&REQUEST=GetCapabilities&SERVICE=WMS">load service</a>


  <a mb-action="source.add.wms" mb-layer-merge="1" mb-wms-merge="1" 
  mb-wms-layers="Gewaesser,Fluesse" 
  mb-url="http://wms.wheregroup.com/cgi-bin/germany.xml?VERSION=1.1.1&REQUEST=GetCapabilities&SERVICE=WMS" href="">load service</a>


.. code-block:: yaml

    mb-action="source.add.wms"    # definiert die Aktion, um einen WMS hinzuzufügen
    mb-wms-merge="1"              # fügt den WMS nur einmal hinzu, wenn der WMS in der Applikation bereits Bestandteil ist, wird dieser verwendet (Standard ist 1)
    mb-layer-merge="1"            # Standard ist 1: aktiviert die Ebene in mb-wms-layers. Deaktiviert die Ebenen nicht, die schon aktiviert sind.
    mb-wms-layers="Gewaesser,Fluesse" # Definiert die Ebenen, die aktiviert werden sollen, _all activates aktiviert alle Ebenen. Standard ist alle Ebenen sind deaktiviert.
    href oder mb-url              # verweist auf die WMS getcapabilities URL



Class, Widget & Style
============================

* **Class:** Mapbender\\CoreBundle\\Element\\FeatureInfoExt
* **Widget:** mapbender.element.featureInfoext.js
* **Style:** mapbender.elements.css

HTTP Callbacks
==============

Keine.

JavaScript API
==============

activate
--------

Aktiviert das Modul, welches dann auf einen Mausklick wartet, um die Infoabfrage zu öffnen und die Erweiterung zu starten.

deactivate
----------
Deaktiviert das Modul.

JavaScript Signals
==================

Keine.
