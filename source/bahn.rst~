
Bahn
====
In dieser Gruppe werden alle Objekte im Bahnareal aus der amtlichen Vermessung auf deren Vollständigkeit und Richtigkeit in der Lage so wie in der Darstellung überprüft. Die SBB-Daten für eine allfällige Korrektur der AV-Daten sind via AGI zu beziehen.

.. note::
   Unter Berücksichtigung von Sonderregelungen (z.B. Gebäude und Strassen) sind überflüssige Unterteilungslinien zu löschen. 

Folgende Objekte werden geprüft:

=============================  ========================================
Topic  		               Art    
=============================  ========================================
Bodenbedeckung                 Bahn
Einzelobjekt                   Lärmschutzwand
Einzelobjekt                   Bahnsteig
Einzelobjekt                   Bahngeleise
Einzelobjekt                   Bahngeleise_ueberdeckt      
=============================  ========================================

BB.Bahn
------- 
.. index:: Bahn
                               

Lagedifferenz  
^^^^^^^^^^^^^                                              
Wird eine Lagedifferenz zwischen der AV und dem aktuellen Orthofoto grösser als die Toleranz (siehe :ref:`ref_Tz`) detektiert, so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz, wird das Objekt nicht angepasst. 



.. code-block:: none

    Bahn / Lagekontrolle   
                                
Beispiele:


+-----------------------------------------------------------------------+-------------------------------------------------------------------------+
|.. _bahn_bahn_Lagedifferenz:                                           |.. _bahn_bahn_Lagedifferenz_korr:                                        |
|                                                                       |                                                                         |
|.. figure:: _static/bahn_bahn_Lagedifferenz.png                        |.. figure:: _static/bahn_bahn_Lagedifferenz_korr.png                     |
|   :width: 550px                                                       |   :width: 550px                                                         |
|   :target: _static/bahn_bahn_Lagedifferenz.png                        |   :target: _static/bahn_bahn_Lagedifferenz_korr.png                     |
|                                                                       |                                                                         |
|   ``BB.Bahn`` ist zu korrigieren, weil die Lagedifferenz              |   ``BB.Bahn`` ist  gemäss den rot dargestellten Linien zu               |
|   grösser als die Toleranz (TS2: 1.0m) ist.                           |   korrigieren. Die Böschung ist als``BB.übrige_humusierte`` zu erfassen.|
+-----------------------------------------------------------------------+-------------------------------------------------------------------------+

                                                                                                                                                                                       

Objekt fehlt/löschen/umattribuieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Ist auf dem aktuellen Orthofoto ein Objekt ``BB.Bahn`` zu erkennen, das in der AV fehlt, ist dieses im Rahmen der PNF/Homogenisierung neu in der AV zu erfassen. 
Ist in der AV ein Objekt ``BB.Bahn`` vorhanden, das auf dem aktuellen Orthofoto nicht mehr zu erkennen ist, ist dieses Objekt zu löschen oder umzuattribuieren. 
Zu ``BB.Bahn`` gehört die Kofferung, die mit Schotter, Kies oder Sand belegten Flächen, Kabelkanäle entlang der Bahnlinien und die Bahnsteige, die zwischen oder neben den Geleisen liegen. Bahndamm (Böschung) gehört nicht zur ``BB.Bahn``.

                                                                                                                                                                   
Benötigende Layer im QGIS:

.. code-block:: none

   Bahn / Lagekontrolle  


Darstellung nicht nach Richtlinie  
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^     
Bei Niveauübergängen geht die BB-Art Strasse_Weg der BB-Art Bahn vor.
 
EO.Laermschutzwand
------------------
siehe :ref:`ref_laermschutz`

EO.Bahnsteig
------------                                                                                                                                                   
Lagedifferenz  
^^^^^^^^^^^^^                                              
Wird eine Lagedifferenz zwischen der AV und dem aktuellen Orthofoto grösser als die Toleranz (siehe :ref:`ref_Tz`) detektiert, so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz, wird das Objekt nicht angepasst.

Benötigende Layer im QGIS:

.. code-block:: none

    Bahn / Lagekontrolle   


Objekt fehlt/löschen/umattribuieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Ist auf dem aktuellen Orthofoto ein Perron zu erkennen, das in der AV fehlt, ist dieses im Rahmen der PNF/Homogenisierung neu in der AV zu erfassen. Ist in der AV ein Perron vorhanden, das auf dem aktuellen Orthofoto nicht mehr zu erkennen ist, ist dieses Objekt zu löschen oder umzuattribuieren.

Benötigende Layer im QGIS:

.. code-block:: none

    Bahn / Lagekontrolle   


Darstellung nicht nach Richtlinie  
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^     
``EO.Bahnsteig`` ist ein Flächenelement.

Benötigende Layer im QGIS:

.. code-block:: none

    Bahn / Lagekontrolle   


EO.Bahngeleise
--------------
Lagedifferenz  
^^^^^^^^^^^^^   
Wird eine Lagedifferenz zwischen der AV und den SBB-Daten detektiert, so ist das Objekt in der AV zu korrigieren. ???? Muss Toleranz (hier ungleich :ref:`ref_Tz`) quantifiziert werden? Z.B. liegt ausserhalb der dickeren blauen Linie (SBB-Datensatz) in QGIS?

Benötigende Layer im QGIS:

.. code-block:: none

    Bahn / Lagekontrolle   

Beispiele:

+--------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+ 
|.. _bahn_bahngleis_Lagedifferenz:                                                           |.. _bahn_bahngleis_Lagedifferenz_korr:                                              | 
|                                                                                            |                                                                                    |
|.. figure:: _static/bahn_bahngleis_Lagedifferenz.png                                        |.. figure:: _static/bahn_bahngleis_Lagedifferenz_korr.png                           | 
|   :width: 550px                                                                            |   :width: 550px                                                                    |
|   :target: _static/bahn_bahngleis_Lagedifferenz.png                                        |   :target: _static/bahn_bahngleis_Lagedifferenz_korr.png                           |
|                                                                                            |                                                                                    |
|   ``EO.Bahngeleise`` ist zu korrigieren gemäss den SBB-Daten.                              |   ``EO.Bahngeleise`` ist zu korrigieren gemäss der rot gestrichelten Linie.        |
+--------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+ 


Objekt fehlt/löschen/umattribuieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Fehlende Objekte sind neu in der AV zu erfassen und nicht mehr vorhandene Bahngeleise sind zu löschen. Bahngeleise im Tunnel sind als ``EO.Bahngeleise_ueberdeckt`` zu attribuieren.

Benötigende Layer im QGIS:

.. code-block:: none

    Bahn / Lagekontrolle   

Darstellung nicht nach Richtlinie  
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^     
``EO.Bahngeleise`` werden bei Unterführungen nicht unterbrochen???? Handbuch SO noch nicht so aber KKVA so..... Was ist wenn Gleis durch Industriehalle geht?

Benötigende Layer im QGIS:

.. code-block:: none

    Bahn / Lagekontrolle   


EO.Bahngeleise_ueberdeckt
-------------------------
Wird eine Lagedifferenz zwischen der AV und den SBB-Daten detektiert, so ist das Objekt in der AV zu korrigieren. ???? Muss Toleranz (hier ungleich :ref:`ref_Tz`) quantifiziert werden? Z.B. liegt ausserhalb der dickeren blauen Linie (SBB-Datensatz) in QGIS? 

Benötigende Layer im QGIS:

.. code-block:: none

    Bahn / Lagekontrolle   

Objekt fehlt/löschen/umattribuieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Fehlende Objekte sind neu in der AV zu erfassen und nicht mehr vorhandene Bahngeleise sind zu löschen. Bahngeleise nicht im Tunnel sind als ``EO.Bahngeleise`` zu attribuieren.

Benötigende Layer im QGIS:

.. code-block:: none

    Bahn / Lagekontrolle   
    Bahn / SBB-Gleisnetz

Darstellung nicht nach Richtlinie  
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^     
``EO.Bahngeleise`` ist ein Linienelement.

Benötigende Layer im QGIS:

.. code-block:: none

    Bahn / Lagekontrolle   

|

                                                                    
