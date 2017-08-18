Konfiguration von Diensten
================================================================================
Sie können die Dienste Ihrer Anwendung konfigurieren. Dies ist sinnvoll, wenn Sie beispielsweise Ebenen ausblenden, die Reihenfolge oder Titel der Ebenen ändern, die Info-Abfrage für einzelne Ebenen verhindern oder Maßstabseinstellungen für Layer vornehmen möchten.

#. Wählen Sie  ``Anwendung -->`` |mapbender3-button-edit| ``Editier-Button --> Layerset --> Editier-Button``, um eine Instanz zu konfigurieren.

#. Im oberen Bereich der Seite können Sie die allgemeinen Informationen des Dienstes konfigurieren. Die Erklärung der einzelnen Begrifflichkeiten folgt unter `Dienstekonfiguration`_.

#. Im unteren Bereich der Seite sehen Sie eine Tabelle mit den Layern des Dienstes.

#. Sie können die Reihenfolge der Layer per Drag & Drop verändern.


.. image:: ../../figures/mapbender3_wms_application_settings.png


**Dienstekonfiguration:**

* Titel: Der Name, der für den Dienst angezeigt wird.
* Format: Wählen Sie das Format für den getMap-Request. Hier können Sie üblicherweise zwischen verschiedenen Bilddateiformaten- & konfigurationen wählen.
* Infoformat: Hier wählen Sie das Format für die getFeatureInfo-Requests.
* Exceptionformat: Wählen Sie das Format, in dem eventuelle Fehlermeldungen ausgegeben werden.
* Opacity: An dieser Stelle können Sie die Opazität (Deckkraft) in Prozent Ihres gesamten WMS wählen. Dabei entspricht die Zahl 0 einem transparenten Layer und die 100 einem Layer mit voller Deckkraft.
* Kachel-Puffer (Tile buffer): Dieser Parameter gilt für Dienste, die gekachelt angefordert werden und gibt an, ob weitere umgebende Kacheln abgerufen werden sollen. Damit sind diese bei einer Pan-Bewegung schon heruntergeladen und sichtbar. Je höher der Wert, desto mehr umgebende Kacheln werden abgerufen. Default: 0.
* BBOX-Faktor: Dieser Parameter gilt für Dienste, die nicht gekachelt angefordert werden. Hier kann die Größe des Bildes angegeben werden. Ein Wert größer als 1 wird ein größeres Kartenbild anfordern. Default: 1.25, kann auf 1 gesetzt werden.
* Sichtbarkeit (Visible): Diese Checkbox bestimmt, ob der Dienst sichtbar angezeigt werden soll oder nicht.
* Basesource: Diese Checkbox definiert, ob der WMS als Basesource angefordert werden soll (Basesources können beim Ebenenbaum ein-/ausgeblendet werden).
* Proxy: Bei Aktivierung der Checkbox wird der Dienst über Mapbender angefordert.
* Transparenz: Standard ist aktiviert, deaktiviert wird der Dienst ohne transparenten Hintergrund angefordert (das entspricht einem getMap-Request mit TRANSPARENT=FALSE).
* Gekachelt (Tiled): Hierüber wird der Dienst in Kacheln angefordert, Standard ist nicht gekachelt. Das Kacheln des Dienstes kann bei einer großen Karte sehr hilfreich sein, sofern der Dienst die Kartengröße nicht unterstützt.

Die Konfigurationen mit einem roten Stern sind Pflichtangaben.
  
**Vendor Specific Parameter:**

In einer Layerset Instanz können Vendor Specific Parameter angegeben werden,
die an den WMS Request angefügt werden. Die Umsetzung folgt den Angaben der
multi-dimensionalen Daten in der WMS Spezifikation.

In Mapbender3 können die Vendor Specific Parameter genutzt werden, um Benutzer und Gruppeninformation des angemeldeten Benutzers an die WMS Anfrage zu
hängen. Es können auch feste Werte übermittelt werden.

Das folgende Beispiel zeigt die Definition eines Parameters „group“, der als
Inhalt die Gruppe des gerade in Mapbender angemeldeten Nutzers weitergibt.

.. image:: ../../figures/mapbender3_vendor_specific_parameter.png

* Type: „single“, „multiple“, „interval“ (multiple Values in Dimensions)
* Name: Parameter Name im WMS Request.
* Default: Standardwert.
* Extent: Verfügbare Werte (wird unter Multiple als kommaseparierte Liste eingetragen).
* Vstype: Mapbender-spezifische Variablen: Gruppe (groups), User (users), Simple.
* Hidden: Wenn dieser Wert gesetzt wird, werden die Anfragen serverseitig versendet, sodass die Parameter nicht direkt sichtbar sind.

Momentan eignet sich das Element, um den Dienst nur an bestimmte Benutzer und Gruppen
weiterzugeben. Dies geschieht z.B. für Benutzer über die $id$ und für Gruppen über den Parameter
$groups$.


**Layerkonfiguration:**

Über die verschiedenen Checkboxen können Sie verschiedene Einstellungen treffen. Beachten Sie dabei, dass die oberste Checkbox der Liste jeweils für alle Instanzen denselben Status auswählt.

* Titel: Layertitel der Service Information (anpassbar).
* Aktiv an/aus (active on/off): Aktiviert / deaktiviert ein Thema in dieser Anwendung. Sobald dieser Haken nicht gesetzt ist, werden alle anderen Haken derselben Instanz ignoriert.
* Auswählen erlauben (select allow): Der Layer ist im Ebenenbaum auswählbar.
* Auswählen an (select on): Der Layer ist bei Anwendungsstart im Ebenenbaum aktiv.
* Info erlauben (info allow): Die Infoabfrage wird für diesen Layer zugelassen.
* Info an (info on): Die Infoabfrage wird beim Start aktiviert.
* Minimaler/ Maximaler Maßstab (minsc / maxsc): Der Maßstabsbereich, in dem der Layer angezeigt wird.
* Aufklappen (toggle): Aufklappen des Layers beim Start der Anwendung.
* Sortieren (reorder): Die Ebenen können über Drag & Drop in der Anwendung verschoben werden.

* ... -> öffnet einen Dialog mit weiteren Informationen:
* Name: Layername der Service Information (wird beim getMap-Request verwendet und ist nicht veränderbar).
* Style: Wenn ein WMS mehr als einen Stil anbietet, können Sie einen anderen Stil als den Standard - (default) - Stil wählen.
