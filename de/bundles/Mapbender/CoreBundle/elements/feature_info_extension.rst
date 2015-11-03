.. _feature_info_extension:

Feature Info Erweiterung 
***********************

Dieses Element stellt eine Erweiterung des Elements FeatureInfo. Es stellt derzeit zwei spezielle Verhalten für die Infoabfrage bereit:

* erlaube das Hervorheben von Ergebnissen der Info-Abfrage
* erlaube das Hinzuladen von WMS Diensten über die Infoabfrage


Die Erweiterung ermöglicht ein farbliches Hervorheben von Treffern der Info-Abfrage. Hierbei können zwei Farben definiert werden - Farbe für die Treffer, Farbe für den Treffer mit Fokus. 

Diese Funktionalität wird für Punkte, Linien und Fläche unterstützt. Die hervorgehobenen Objekte können in den Druck übergeben werden. Bitte beachten Sie, dass Sie das featureInfo-Template erweitern müssen, um die Funktonalität nutzen zu können. Informationen dazu finden Sie weiter unten unter **Hervorheben von Geometrien**.

Sie können das Hinzuladen von WMS Diensten über einen Link unterstützen. Bitte beachten Sie, dass Sie dazu das featureInfo-Template erweitern müssen. Informationen dazu finden Sie weiter unten unter **Hinzufügen eines WMS über einen definierten Link**.


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

Um diese Funktionalität nutzen zu können, müssen Sie ihr FeatureInfo-Template erweitern. Es bnötigt die Klasse **class="geometryElement"**, **data-srid="EPSG:4326"** mit der Angabe zur Projektion der Daten sowie **data-geometry** mit der WKT Präsentation der Geometrie:

.. code-block:: html

  <table class="geometryElement" data-srid="EPSG:4326" data-geometry="MULTIPOLYGON(...)" >...</table>

If you use PostgreSQL as datasource in your WMS Service, you can use the PostGIS function st_asText(geom) to generate the WKT.





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


deactivate
----------
Deaktiviert das Modul.

JavaScript Signals
==================

Keine.
