Weitere Ebenen
==============
Die in diesem Kapitel zu überprüfenden Objekte sind noch nicht in der QGIS-Fachschale implementiert.

Folgende Objekte werden geprüft:

=============================  ========================================
Tabelle  		       Fehlerart
=============================  ========================================
LFP1 / LFP2                    Punktzeichen nicht erfasst
Hilfsfixpunkte                 Hilfsfixpunkte nicht separat ausgeschieden
Strassenachsen                 Falscher Verlauf
=============================  ========================================


LFP1 / LFP2
-----------
.. index:: LFP2   
                               
Punktzeichen nicht erfasst 
^^^^^^^^^^^^^^^^^^^^^^^^^^
Die Punktzeichen von LFP1 und LFP2 sind zu erfassen. Die korrekte Vermarkungsart ist dem FPDS resp. dem Export (<https://dav0.bgdi.admin.ch/fpds/Interlis/>`_ ) zu entnehmen.


Hilfsfixpunkte
--------------
.. index:: Hilfsfixpunkt

Hilfsfixpunkt nicht separat ausgeschieden
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Hilfsfixpunkte sind nicht in der Tabelle LFP3 zu führen sondern separat in der Tabelle Hilfsfixpunkte. Erlaubte Vermarkungsarten sind: ``unversichert`` und ``weitere``. 


Strassenachsen
--------------
.. index:: Strassenachsen

Falscher Verlauf
^^^^^^^^^^^^^^^^
Liegen die Strassenachsen nach einer Lagekorrektur der Bodenbedeckungsart ``Strasse_Weg`` **ausserhalb** derselben, so sind die Achsen so zu korrigieren, dass sie wieder innerhalb der Strasse resp. des Weges liegen. Nicht korrigiert werden Achsen, die aufgrund einer Korrektur der Bodenbedeckung nicht mehr korrekt in der Mitte der Strasse resp. des Weges liegen.
Attribut IstAchse ist hier auf ``Nein`` zu setzen 
