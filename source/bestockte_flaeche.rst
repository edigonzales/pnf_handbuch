.. _ref_BestockteFlaechen:

Bestockte Fläche
=====================
Bei dieser Gruppe werden alle bestockten Flächen aus der amtlichen Vermessung auf deren Vollständigkeit und Richtigkeit in der Lage so wie in der Darstellung überprüft.

Folgende Objekte werden geprüft:

=============================  ========================================
Topic  		               Art    
=============================  ========================================
Bodenbedeckung                 geschlossener Wald
Bodenbedeckung                 Parkanlage bestockt
Bodenbedeckung                 Hecke
Bodenbedeckung		       übrige bestockte	
Einzelobjekt                   schmale best. Fläche
=============================  ========================================

.. note::
   Das Orthofoto mit der Darstellung des Infrarot-Kanals kann für eine bessere Interpretation der bestockten Flächen dienen.

+-------------------------------------------------------------------------------+------------------------------------------------------------------------------------+ 
|.. _Orthofoto_RGB:                                                             |.. _Orthofoto_CIR:                                                                  | 
|                                                                               |                                                                                    |
|.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_RGB.png |.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_IR.png       | 
|   :width: 550px                                                               |   :width: 550px                                                                    |
|   :target: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_RGB.png |   :target: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_IR.png       |
|                                                                               |                                                                                    |
|   Orthofoto mit den Kanälen Rot, Grün und Blau.                               |   Orthofoto mit den Kanälen Infrarot, Rot und Grün.                                |
+-------------------------------------------------------------------------------+------------------------------------------------------------------------------------+


BB.geschlossener_Wald
---------------------  
.. index:: Wald, geschlossener Wald   
                               
Lagedifferenz  
^^^^^^^^^^^^^                        
                         
Wird eine Lagedifferenz zwischen der AV und dem aktuellen Orthofoto grösser als die Toleranz (siehe :ref:`ref_Tz`) und die Interpretationsgenauigkeit detektiert, so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz, wird das Objekt nicht angepasst. 

Benötigende Layer im QGIS:

.. code-block:: none

   Bestockte Fläche / Lagekontrolle   
                                

Beispiele:

+--------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+ 
|.. _bestockte_Flaeche_geschlossener_Wald_Lagedifferenz:                                     |.. _bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_korr:                        | 
|                                                                                            |                                                                                    |
|.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz.png                  |.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_korr.png     | 
|   :width: 550px                                                                            |   :width: 550px                                                                    |
|   :target: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz.png                  |   :target: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_korr.png     |
|                                                                                            |                                                                                    |
|   ``BB.geschlossener_Wald`` ist zu korrigieren, weil die Lagedifferenz                     |   ``BB.geschlossener_Wald`` ist zu korrigieren gemäss den rot dargestellten Linie  |
|   grösser als die Toleranz (TS3: 3.0 m) und Interpretationsgenauigkeit ist.                |                                                                                    |
+--------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+        
|.. _bestockte_Flaeche_geschlossener_Wald_Lagedifferenz2:                                    |.. _bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_korr2:                       | 
|                                                                                            |                                                                                    |
|.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz2.png                 |.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz2_korr.png    | 
|   :width: 550px                                                                            |   :width: 550px                                                                    |
|   :target: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz2.png                 |   :target: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz2_korr.png    |
|                                                                                            |                                                                                    |
|   ``BB.geschlossener_Wald`` ist zu korrigieren, weil die Lagedifferenz                     |   ``BB.geschlossener_Wald`` ist zu korrigieren gemäss den rot dargestellten Linie  |
|   grösser als die Toleranz (TS3: 3.0 m) und Interpretationsgenauigkeit ist.                |                                                                                    |
+--------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+ 
|.. _bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_iO:                                  |                                                                                    | 
|                                                                                            |                                                                                    |
|.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_iO.png               |                                                                                    | 
|   :width: 550px                                                                            |                                                                                    |
|   :target: _static/bestockte_Flaeche_geschlossener_Wald_Lagedifferenz_iO.png               |                                                                                    |
|                                                                                            |                                                                                    |
|   ``BB.geschlossener_Wald`` ist **nicht** zu korrigieren, weil die                         |                                                                                    |
|   Lagedifferenz  grösser als die Toleranz (TS3: 3.0 m) und Interpretationsgenauigkeit ist. |                                                                                    |
+--------------------------------------------------------------------------------------------+------------------------------------------------------------------------------------+ 

Objekt fehlt/löschen
^^^^^^^^^^^^^^^^^^^^
Ist auf dem aktuellen Orthofoto ein geschlossener Wald zu erkennen, welcher das Flächenkriterium von 500m2 erfüllt und die Breite > 12m ist, ist dieser im Rahmen der PNF/Homogenisierung neu in der AV zu erfassen. Ist in der AV ein geschlossener Wald vorhanden, der auf dem aktuellen Orthofoto nicht mehr zu erkennen ist, ist dieses Objekt zu löschen. 
                                                                                                                                                                   
Benötigende Layer im QGIS:

.. code-block:: none

   Bestockte Fläche / Lagekontrolle  



Beispiel:
                                                                     
.. _Gewaesser_stehendes_Gewaesser_loeschen:                                                                                                                                                               
                                                                     
.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_fehlt.png       
   :width: 550px                                                     
   :target: _static/bestockte_Flaeche_geschlossener_Wald_fehlt.png         
   
   ``BB.geschlossener_Wald`` fehlt und ist deshalb neu zu erfassen. 
                                                               

                                                                      
Objekt umattribuieren
^^^^^^^^^^^^^^^^^^^^^                                                                                                                                                                                                                            
Ist in der AV geschlossener Wald erfasst, der das Flächenkriterium von 500m2 und die Breite > 12m nicht erfüllen, sind diese umzuattribuieren.    

.. note::
   | Waldstücke die durch ``BB.Strasse_Weg`` getrennt werden, gehören zu ``BB.geschlossener_Wald``. Einzelne Teilflächen sind für die Beurteilung des Flächenkriteriums als ein Fläche zu betrachten.
   | Waldzungen deren Breite zwischen 6 m und 12 m liegt, werden ab einer Länge von 20 m nicht mehr als ``BB.geschlossener_Wald`` attribuiert. Waldzungen mit einer Breite kleiner 6 m gehören nicht zu ``BB.geschlossener_Wald``.
   
Benötigende Layer im QGIS:

.. code-block:: none

   Bestockte Fläche / Lagekontrolle 

Beispiele:

+-----------------------------------------------------------------------------+------------------------------------------------------------------------------------+ 
|.. _bestockte_Flaeche_geschlossener_Wald_umattribuieren:                     |.. _bestockte_Flaeche_geschlossener_Wald_umattribuieren_korr:                       | 
|                                                                             |                                                                                    |
|.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_umattribuieren.png  |.. figure:: _static/bestockte_Flaeche_geschlossener_Wald_umattribuieren_korr.png    | 
|   :width: 550px                                                             |   :width: 550px                                                                    |
|   :target: _static/bestockte_Flaeche_geschlossener_Wald_umattribuieren.png  |   :target: _static/bestockte_Flaeche_geschlossener_Wald_umattribuieren_korr.png    |
|                                                                             |                                                                                    |
|   ``BB.geschlosener Wald`` > 12m ist umzuattribuieren in ``BB.Hecke``.      |   ``BB.geschlossener Wald`` ist zu korrigieren gemäss den rot dargestellten Linien.|
+-----------------------------------------------------------------------------+------------------------------------------------------------------------------------+                     

BB.uebrige_Bestockte
--------------------
.. index:: übrige Bestockte  
                               
Lagedifferenz  
^^^^^^^^^^^^^                        
                         
Wird eine Lagedifferenz zwischen der AV und dem aktuellen Orthofoto grösser als die Toleranz (siehe :ref:`ref_Tz`) und die Interpretationsgenauigkeit detektiert, so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz un der Interpretationsgenauigkeit, wird das Objekt nicht angepasst. 

Benötigende Layer im QGIS:

.. code-block:: none

   Bestockte Fläche / Lagekontrolle   
                                


Objekt umattribuieren
^^^^^^^^^^^^^^^^^^^^^ 
Sind in der AV ``BB.uebrige_Bestockte``-Objekte erfasst, die zu ``BB.Hecke`` oder ``BB.geschlossener_Wald`` gehören, sind diese umzuattribuieren.

.. note::
   Aufforstungen gehören zu ``BB.geschlossener_Wald``.

Beispiel:

+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------+                                                                     
|.. _bestockte_Flaeche_uebrige_Bestockte_umattribuieren:                      |.. _bestockte_Flaeche_uebrige_Bestockte_umattribuieren2:                           | 
|                                                                             |                                                                                   |
|.. figure:: _static/bestockte_Flaeche_uebrige_Bestockte_umattribuieren.png   |.. figure:: _static/bestockte_Flaeche_uebrige_Bestockte_umattribuieren2.png        | 
|   :width: 550px                                                             |   :width: 550px                                                                   |
|   :target: _static/bestockte_Flaeche_uebrige_Bestockte_umattribuieren.png   |   :target: _static/bestockte_Flaeche_uebrige_Bestockte_umattribuieren2.png        |
|                                                                             |                                                                                   |
|   ``BB.uebrige_Bestocke`` ist umzuattribuieren in ``BB.geschlossener_Wald``.|   ``BB.uebrige_bestocke`` ist umzuattribuieren in ``BB.Hecke``.                   |  
+-----------------------------------------------------------------------------+-----------------------------------------------------------------------------------+ 

Objekt fehlt/löschen  
^^^^^^^^^^^^^^^^^^^^
Ist auf dem aktuellen Orthofoto eine Bestockung zu erkennen, die das Flächenkriterium von 500m2 nicht erfüllt (``BB.geschlossener Wald``) und eine Breite > 12 m aufweist, ist diese bestockte Fläche im Rahmen der PNF/Homogenisierung neu in der AV als ``BB.uebrige_Bestockte`` zu erfassen. Ist in der AV ein Objekt der Art``BB.uebrige_Bestockte`` vorhanden, das auf dem aktuellen Orthofoto nicht mehr zu erkennen ist, ist dieses Objekt zu löschen. 

Benötigende Layer im QGIS:

.. code-block:: none

   Bestockte Fläche / Lagekontrolle  


BB.Hecke
---------
.. index:: Hecke
                               
Lagedifferenz  
^^^^^^^^^^^^^                        
                         
Wird eine Lagedifferenz zwischen der AV und dem aktuellen Orthofoto grösser als die Toleranz (siehe :ref:`ref_Tz`) und die Interpretationsgenauigkeit detektiert, so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz und der Interpretationsgenauigkeit, wird das Objekt nicht angepasst. 

Benötigende Layer im QGIS:

.. code-block:: none

   Bestockte Fläche / Lagekontrolle   

Objekt fehlt/löschen
^^^^^^^^^^^^^^^^^^^^^
Ist auf dem aktuellen Orthofoto ein Bestockung zu erkennen, die das Flächenkriterium gemäss TVAV Art. 13 (???????????) erfüllt, ist diese bestockte Fläche im Rahmen der PNF/Homogenisierung neu in der AV als ``BB.Hecke`` zu erfassen. 
Ist in der AV eine ``BB.Hecke`` erfasst, die auf dem aktuellen Orthofoto nicht mehr zu erkennen ist oder das Flächenkriterium gemäss TVAV Art. 13 nicht nicht erfüllt, ist dieses Objekt zu löschen.

Beispiel:

.. _bestockte_Flaeche_Heck_loeschen:                             
                               
.. figure:: _static/bestockte_Flaeche_Heck_loeschen.png
   :width: 550px               
   :target: _static/bestockte_Flaeche_Heck_leoschen.png  
                                                                  
   Beide ``BB.Hecke`` sind zu löschen, da diese das Flächenkriterium (TS3: 1000 m2) nicht erfüllen. 
    


Objekt umattribuieren
^^^^^^^^^^^^^^^^^^^^^ 
Sind in der AV Hecken erfasst, die gemäss Kriterium *Handbuches der amtlichen Vermessung Kanton Solothurn*  zu ``BB.übrige Bestockte`` oder ``BB.geschlossener Wald`` gehören, sind sie dementsprechend anzupassen.


                
.. code-block:: none

   Bestockte Fläche / Lagekontrolle          


Beispiel:

.. _bestockte_Flaeche_Heck_umattribuieren:                             
                               
.. figure:: _static/bestockte_Flaeche_Heck_umattribuieren.png
   :width: 550px               
   :target: _static/bestockte_Flaeche_Heck_umattribuieren.png  
                                                                  
   ``BB.Hecke`` ist umzuattribuieren in ``BB.geschlossener Wald``. Weil die Bachbreite kleiner 4m ist, wird die Bestockung als zusammenhängende Einheit betrachtet.
|
                                                                   
  
   
                                                                                                                                                   
                                                                    
