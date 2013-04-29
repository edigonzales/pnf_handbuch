Landwirtschaft
==============
In dieser Gruppe werden folgende Objekte der Bodenbedeckung auf ihre Richtigkeit geprüft:

==================  ==================
Topic  		    Art    
==================  ================== 
Bodenbedeckung      Acker_Wiese 
Bodenbedeckung      Weide
Bodenbedeckung      Reben
Bodenbedeckung      Obstkultur
Bodenbedeckung      uebrige_Intensivkultur
==================  ==================

BB.Acker_Wiese / BB.Weide
-------------------------
.. index:: Acker, Wiese, Weide

Objekt umattribuieren
^^^^^^^^^^^^^^^^^^^^^
Falsch attribuierte Acker_Wiesen und Weiden sind der richtigen Bodenbedeckungsart zuzuweisen. Lagedifferenzen zwischen ``BB.Gartenanlage`` resp. bestockten Flächen und ``BB.Acker_Wiese`` resp. ``BB.Weide`` sind in den Mängelgruppen :ref:`ref_BebautesGebiet` und :ref:`ref_BestockteFlaechen` zu erfassen.

Benötigte Layer in QGIS:

.. code-block:: none

   Landwirtschaft / Lagekontrolle
   Landwirtschaft / Checklayer / Acker_Wiese in TS2 (TODO)
   Landwirtschaft / Checklayer / Weide in TS2 (TODO)

Beispiele:

.. _fig_landw_1:

.. figure:: _static/Landwirtschaft_umattribuieren_Acker_Wiese.png
   :width: 450px
   :target: _static/Landwirtschaft_umattribuieren_Acker_Wiese.png

   Die beiden Acker_Wiesen-Objekte (rosa Linie) sind in ``BB.Gartenanlage`` umzuattribuieren.


BB.Weide
--------
.. Weide 

Objekt umattribuieren
^^^^^^^^^^^^^^^^^^^^^
Die Unterscheidung zwischen ``BB.Acker_Wiese`` und ``BB.Weide`` wird nicht länger gemacht. Weiden sind als ``Acker_Wiese`` zu attribuieren und Unterteilungslinien zu löschen. 

Benötigte Layer in QGIS:

.. code-block:: none

   Landwirtschaft / Checklayer / BB.Weide


BB.Reben / BB.Obstkultur / BB.uebrige_Intensivkulturen
------------------------------------------------------
.. index:: Reben, Obstkultur, übrige Intensivkulturen  

Die drei Bodenbedeckungsarten ``BB.Reben``, ``BB.Obstkultur`` und ``BB.uebrige_Intensivkulturen`` sind auf ihre Vollständigkeit, Aktualität sowie Lagekorrektheit zu prüfen:

Lagedifferenz
^^^^^^^^^^^^^
Die korrekte Lage ist mit dem aktuellen Orthofoto zu prüfen. Korrigiert werden Abweichungen ausserhalb der Toleranzbereiche (siehe :ref:`ref_Tz`)

Benötigte Layer in QGIS:

.. code-block:: none

   Landwirtschaft / Lagekontrolle
   Landwirtschaft / Checklayer / BB.Kulturen < 1000 m2

Beispiele:

+---------------------------------------------------------------------+-----------------------------------------------------------------------+
|.. _fig_landw_2:                                                     |.. _fig_landw_3:                                                       |
|                                                                     |                                                                       |
|.. figure:: _static/Landwirtschaft_Lagedifferenz_Kulturen.png        |.. figure:: _static/Landwirtschaft_Lagedifferenz_Kulturen_korr.png     |
|   :width: 550px                                                     |   :width: 550px                                                       |
|   :target: _static/Landwirtschaft_Lagedifferenz_Kulturen.png        |   :target: _static/Landwirtschaft_Lagedifferenz_Kulturen_korr.png     |
|                                                                     |                                                                       |
|   ``BB.Obstkultur`` (gelbe Linie) ist zu korrigieren.               |   Die Obstkultur kann ausgeschieden werden (rote Linie) werden sofern |
|                                                                     |   sie grösser 1000 m2 ist.                                            |
+---------------------------------------------------------------------+-----------------------------------------------------------------------+

Objekt fehlt
^^^^^^^^^^^^
Fehlende Objekte sind zu erfassen sofern sie grösser 1000 m2 sind.

Benötigte Layer in QGIS:

.. code-block:: none

   Landwirtschaft / Lagekontrolle


Objekt löschen
^^^^^^^^^^^^^^
Zu kleine oder nicht mehr vorhanden Intensivkulturen sind zu löschen.

Benötigte Layer in QGIS:

.. code-block:: none

   Landwirtschaft / Lagekontrolle
   Landwirtschaft / Checklayer / BB.Kulturen < 1000 m2

Alle Objekte
------------
Überflüssige Unterteilungslinien sind zu löschen.

|

.. index:: Acker, Wiese, Weide, Acker_Wiese, Reben, Intensivkultur, uebrige_Intensivkultur

