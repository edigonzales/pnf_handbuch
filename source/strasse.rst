Strasse
=======
Bei diese Gruppe werden alle Elemente der Stassen aus der amtlichen Vermessung auf dessen Vollständigkeit und Richtigkeit in der Lage so wie in der Darstellung überprüft.

Folgende Objekte werden geprüft:

==================  ==================
Topic  		    Art    
==================  ================== 
Bodenbedeckung      Strasse_Weg
Bodenbedeckung      Trottoir
Bodenbedeckung      Verkehrsinsel
Bodenbedeckung      übrige_befestigte
Bodenbedeckung      übrige_humusierte
Einzelobjekt	    Lärmschutzwand
Einzelobjekt        Tunnel_Unterführung_Galerie
Einzelobjekt        Brücke_Passerelle
Einzelobjekt        Pfeiler
Einzelobejkt        schnaler_Weg
Einzelobjekt        Fahrspur
==================  ==================



BB.Strasse_Weg  
--------------  
.. index:: Strasse, Weg      
                               
Lagedifferenz  
^^^^^^^^^^^^^                        
                         
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) detektiert so ist das Objekt in der AV zu korrigieren.                                                 
Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst. Ist die Lagekontrolle mit dem Orthofoto auf Grund von interpertier Schwierigkeit (z.B. durch 
Schatten oder Sichthindernisse wie Bäume) nicht möglich kann eine Feldkontrolle sinnvoll sein. 

Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle   
                                

Beispiele:
                              
+---------------------------------------------------------------------+-----------------------------------------------------------------------+
|.. _Strasse_Lagedifferenz_Kreuzung:                                  |.. _Strasse_Lagedifferenz_Kreuzung_korr:                               |
|                                                                     |                                                                       |
|.. figure:: _static/Strasse_Lagedifferenz_Kreuzung.png               |.. figure:: _static/Strasse_Lagedifferenz_Kreuzung_korr.png            |
|   :width: 550px                                                     |   :width: 550px                                                       |
|   :target: _static/Strasse_Lagedifferenz_Kreuzung.png               |   :target: _static/Strasse_Lagedifferenz_Kreuzung_korr.png            |
|                                                                     |                                                                       |
|   ``BB.Strasse_Weg`` ist zu korrigieren, weil die Lagedifferenz     |   ``BB.Strasse_Weg`` ist zu korrigieren gemäss den rot dargestellten  |
|   grösser als die Toleranz (TS3: 1.5m) ist.                         |   Linien.                                                             |
+---------------------------------------------------------------------+-----------------------------------------------------------------------+
|.. _Strasse_Lagedifferenz_TS2:                                       |.. _Strasse_Lagedifferenz_TS2_korr:                                    |
|                                                                     |                                                                       |
|.. figure:: _static/Strasse_Lagedifferenz_TS2.png                    |.. figure:: _static/Strasse_Lagedifferenz_TS2_korr.png                 |   
|   :width:  550px                                                    |   :width:  550px                                                      |
|   :target: _static/Strasse_Lagedifferenz_TS2.png                    |   :target: _static/Strasse_Lagedifferenz_TS2_korr.png                 |
|                                                                     |                                                                       |
|   ``BB.Strasse_Weg`` ist zu korrigieren, weil die Lagedifferenz     |   ``BB.Strasse_Weg`` ist zu korrigieren gemäss den rot dargestellten  |
|   grösser als die Toleranz (bebautes Gebiet: 0.5 m) ist.            |   Linien.                                                             |
+---------------------------------------------------------------------+-----------------------------------------------------------------------+
|.. _Strasse_Lagedifferenz_TS3:                                       |.. _Strasse_Lagedifferenz_TS4:                                         |
|                                                                     |                                                                       |
|.. figure:: _static/Strasse_Lagedifferenz_TS3.png                    |.. figure:: _static/Strasse_Lagedifferenz_TS4.png                      |     
|   :width:  550px                                                    |   :width:  550px                                                      |
|   :target: _static/Strasse_Lagedifferenz_TS3.png                    |   :target: _static/Strasse_Lagedifferenz_TS4.png                      |
|                                                                     |                                                                       |
|   ``BB.Strasse_Weg`` ist **nicht** zu korrigieren, weil die         |   ``BB.Strasse_Weg`` ist **nicht** zu korrigieren, weil die           |
|   Lagedifferenz kleiner als die Toleranz (TS3: 1.5 m) ist.          |   Lagedifferenz kleiner als die Toleranz (TS4: 1.5 m) ist.            |
+---------------------------------------------------------------------+-----------------------------------------------------------------------+


Objekt fehlt/Löschen  
^^^^^^^^^^^^^^^^^^^^
Ist auf dem aktuellen Orthofoto eine befestigte Strasse/Weg zu erkennen, die nicht als Bodenbedeckung oder als Einzelobjekt in der AV vorhanden ist, ist diese im Rahmen der PNF/Homogenisierung neu zu erfassen. 
Ist in der AV eine befestigte Strasse/Weg vorhanden, die auf dem aktuellen Orthofoto nicht mehr zu erkennen ist und auch die Kriterien der ``EO.Fahrspur`` resp. ``EO.schmaler_Weg`` nicht erfüllt, ist dieses Objekt zu löschen. Ebenfalls zu löschen sind private befestigte Gartenwege.

Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle


Beispiele:


+---------------------------------------------------------------------+-----------------------------------------------------------------------+
|.. _Strasse_fehlt:                                                   |.. _Strasse_loeschen:                                                  |
|                                                                     |                                                                       |
|.. figure:: _static/Strasse_fehlt_TS3.png                            |.. figure:: _static/Strasse_loeschen.png                               |
|   :width: 550px                                                     |   :width: 550px                                                       |
|   :target: _static/Strasse_fehlt_TS3.png                            |   :target: _static/Strasse_leoschen.png                               |
|                                                                     |                                                                       |
|   ``BB.Strasse_Weg`` fehlt in der  AV. ``BB.Strasse_Weg`` ist zu    |   ``BB.Strasse_Weg`` ist zu löschen                                   |
|   erfassen                                                          |                                                                       |
+---------------------------------------------------------------------+-----------------------------------------------------------------------+

Objekt umattribuieren
^^^^^^^^^^^^^^^^^^^^^                                                                                                                                                                                                                            
Mit dem aktuellen Orthofoto ist zu kontrollieren, ob alle befestigten Strassen und Weg als ``BB.Strasse_Weg`` erfasst sind. Andernfalls müssen die Strassen und Weg umattribuiert werden in ``BB.Strasse_Weg, EO.Fahrspur oder EO.schmaler_Weg``.  
                                                                                                                                                                                                                                                                                                                                     
Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle   
   
Beispiele:                            
                                                                                                                       
                                                                                    
.. _Strasse_umattribuieren:                                              
                                                                                    
.. figure:: _static/Strasse_umattribuieren.png                          
   :width: 550px                                                                    
   :target: _static/Strasse_umattribuieren.png                          
                                                                                    
   ``BB.Strasse_Weg`` ist in ``EO.Fahrspur`` um zu attribuieren
   
              

Darstellung nicht nach Richtlinie  
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^  
BB.Strasse_Weg unterbrochen
+++++++++++++++++++++++++++
Das Objekt ``BB.Strasse_Weg`` darf z.B. bei Hofdurchfahrten oder bei niveaugleichen Kreuzungen nicht unterbrochen sein. Ist dies der Fall, muss dies im Rahmen der PNF/Homogenisierung bereinigt werden. Ziel ist es ein zusammenhängendes Strassen-/Wegnetz zu erhalten. 
Genauere Erläuterung über die Erfassung der Niveauübergänge sind im *Handbuch der amtlichen Vermessung Kanton Solothurn* zu finden.                 
    
Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle 

BB.Strasse_Weg zu grosses Objekt
++++++++++++++++++++++++++++++++
Grosse Strassenobjekte (>10'000 m2) der ``BB.Strasse_Weg`` sind zu unterteilen. Da bekannt ist, dass grosse Objekte bei der Datenverarbeitung Schwierigkeiten bereiten.

Benötigende Layer im QGIS:

.. code-block:: none 

   Stasse/ Checklayer/ BB.Strasse_Weg>10000m2 

BB.Strasse_Weg bei Erschliessung mehrerer Liegenschaften 
++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                                                                                                                                                                                                                                                                       
Strassen und Wege die der Erschliessung mehrerer Liegenschaften oder mehrerer Gebäude dienen und die in der AV als ``BB.GEbäudeerschliessung`` erfasst sind, werden im Rahmen der PNF/Homogenisierung **nicht** korrigiert (siehe :ref:`Beispiel <Strasse_ueber_mehrere_parz>`). 
          

Befestigte Strassenverengungen ohne Höhenunterschied und befahrbarer Teil des Kreisels (Pavé)    
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Befestigte Strassenverengungen ohne Niveauunterschied gehören zu ``BB.Strasse_Weg`` (siehe :ref:`Beispiel <Strasse_Strassenveraengung>`). Das selbe gilt für den befahrbarer Teil des Kreisels (Pavé) (siehe :ref:`Beispiel <Strasse_pave>`).                 

Benötigende Layer im QGIS:

.. code-block:: none                                                                                                        

   Strasse/ Lagekontrolle   
  
  
Parallele Darstellung
+++++++++++++++++++++
Nicht parallele Darstellungen der ``BB.Strasse_Weg`` werden im Rahmen der PNF/Homogenisierung **nicht** korrigiert.


Durch Felspartien überdeckte Strassen
+++++++++++++++++++++++++++++++++++++                                                                                                                                                                                       
Bei den Strassen die durch Felspartien überdeckt sind gelten die Darstellungsrichtline gemäss *Handbuch der amtlichen Vermessung Kanton Solothurn*. Unterscheidet sich die Darstellung in der AV von der von Richtlinie, ist sie entsprechend zu korrigieren.           
                                                                                                                                                                                                                                                             

Beispiele:       

+--------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+
|.. _Strasse_Hofdurchfahrt:                                                            | .. _Strasse_ueber_mehrere_parz:                                                       |
|                                                                                      |                                                                                       |                                                                                                   
|.. figure:: _static/Strasse_Hofdurchfahrt.png                                         | .. figure:: _static/Strasse_ueber_mehrere_parz.png                                    |
|   :width: 550px                                                                      |    :width: 550px                                                                      |
|   :target: _static/Strasse_Hofdurchfahrt.png                                         |    :target: _static/Strasse_ueber_mehrere_parz.png                                    |                              
|                                                                                      |                                                                                       |
|   ``BB.Strasse_Weg`` draf bei Hofdurchfahrten nicht unterbrochen sein.               |    ``BB.Strasse_Weg`` bei Erschliessung mehrerer Liegenschaften wird nicht korrigiert.|                                                                               
|                                                                                      |                                                                                       |
+--------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+   
|.. _Strasse_Strassenveraengung:                                                       | .. _Strasse_pave:                                                                     |
|                                                                                      |                                                                                       | 
|.. figure:: _static/Strasse_Verkehrsveraengung.png                                    | .. figure:: _static/Strasse_pave.png                                                  |
|   :width: 550px                                                                      |    :width: 550px                                                                      |
|   :target: _static/Strasse_Verkehrsveraengung.png                                    |    :target: _static/Strasse_pave.png                                                  |
|                                                                                      |                                                                                       |
|   Befestigte Strassenverengungen ohne Niveauunterschied gehört zu ``BB.Strasse_Weg``.|    Befahrbarer Teil des Kreisels (Pavé) gehört zu ``BB.Strasse_Weg``.                 | 
|                                                                                      |                                                                                       |
+--------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+         
                      

BB.Trottoir                                                                 
-----------  

.. index:: Trottoir

Lagedifferenz  
^^^^^^^^^^^^^
                                                                                                                                                                                 
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) detektiert so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst.

Benötigende Layer im QGIS:

.. code-block:: none 

   Strasse/ Lagekontrolle   
                                

Beispiele:
                              
+---------------------------------------------------------------------+-----------------------------------------------------------------------+
|.. _Trottoir_Lagedifferenz:                                          |.. _Trottoir_Lagedifferenz_korr:                                       |
|                                                                     |                                                                       |
|.. figure:: _static/Strasse_Trottoir_Lagedifferenz.png               |.. figure:: _static/Strasse_Trottoir_Lagedifferenz_korr.png            |
|   :width: 550px                                                     |   :width: 550px                                                       |
|   :target: _static/Strasse_Trottoir_Lagedifferenz.png               |   :target: _static/Strasse_Trottoir_Lagedifferenz_korr.png            |
|                                                                     |                                                                       |
|   ``BB.Trottoir`` ist zu korrigieren, weil die Lagedifferenz        |   ``BB.Trottoir`` ist zu korrigieren gemäss den rot dargestellten     |
|   grösser als die Toleranz (TS2: 0.5m) ist.                         |   Linien.                                                             |
+---------------------------------------------------------------------+-----------------------------------------------------------------------+ 
                                                                                                                                            

Objekt fehlt/ löschen/ umattribuieren      
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^    

Ist auf dem aktuellen Orthofoto eine Trottoir zu erkennen, das nicht in der AV vorhanden ist, ist diese im Rahmen der PNF/Homogenisierung neu zu erfassen. Falls in der AV eine Trottoir vorhanden ist, dass auf dem aktuellen Orthofoto nicht mehr zu erkennen ist, ist dieses Objekt zu löschen oder evtl. einer anderen BB.Art zu zuweisen. 

Benötigende Layer im QGIS:

.. code-block:: none                                                                                                                                                                                                                                                                                                       
                                                                                                                                        
  Strasse/ Lagekontrolle                                                                                                                                                         
  

Darstellung nicht nach Richtlinie    
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^                                        

???? Bei Strasseneinfahrten geht das ``BB.Trottoir`` der ``BB.Strasse_Weg`` vor, wenn das Trottoir baulich nicht unterbrochen ist.  ????? oder wir nicht korrigiert? 


BB.Verkehrsinsel                                                                
----------------  

.. index:: Verkehrsinsel 

Lagedifferenz  
^^^^^^^^^^^^^
                                                                                                                                                                                 
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) detektiert so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst.

Benötigende Layer im QGIS:

.. code-block:: none 

   Strasse/ Lagekontrolle   
                                

                                                                                                                                       
Objekt fehlt/löschen     
^^^^^^^^^^^^^^^^^^^^    

Ist auf dem aktuellen Orthofoto eine Verkehrsinsel zu erkennen, die nicht in der AV vorhanden ist, ist diese im Rahmen der PNF/Homogenisierung neu zu erfassen. 
Falls in der AV eine Verkehrsinsel vorhanden ist, welche auf dem aktuellen Orthofoto nicht mehr zu erkennen ist, ist dieses Objekt zu löschen. Ebenfalls zu löschen sind temporär angelegte Verkehrsinseln oder befestigte Verkehrsinsel ohne Niveauunterschied die in der AV erfasst sind.
 
                                                                                                                                                                                       
Benötigende Layer im QGIS:

.. code-block:: none                                                                                                                                                                                                                                                                                                       
                                                                                                                                        
  Strasse/ Lagekontrolle                                                                                                                                                         
                                                                                                                                                                                                                                                                                        
Objekt umattribieren
^^^^^^^^^^^^^^^^^^^^ 
Verkehrsinsel sind komplett von ``BB.Strasse_Weg`` umgeben. Strassenverengungen die humusiert sind werden als ``BB.uebrige_humusierte`` attribuiert.
Humusierte Trennstreifen z.B. bei Autobahnen oder zwischen Strassen und z.B. Radwegen ist die Bodenbedeckung ``BB.uebrige_humusierte`` und **nicht** ``BB.Verkehrsinsel``.

Benötigende Layer im QGIS

.. code-block:: none     
                         
   Strasse/ Lagekontrolle 

Beispiele:                            
 
+--------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
|.. _Verkehrsinsel_Strassenveraengung:                                                 |.. _Verkehrsinsel_Trennstreifen:                                               |
|                                                                                      |                                                                               |
|.. figure:: _static/Strasse_Verkehrsinsel_Strassenveraengung.png                      |.. figure:: _static/Strasse_Verkehrsinsel_Trennstreifen.png                    |
|   :width: 550px                                                                      |   :width: 550px                                                               |
|   :target: _static/Strasse_Verkehrsinsel_Strassenveraengung.png                      |   :target: _static/Strasse_Verkehrsinsel_Trennstreifen.png                    |
|                                                                                      |                                                                               |
|   Humusierte Strassenverenegungen sind als ``BB.uebrige_humusierte`` zu attribuieren |   Humusierte Trenstreifen sind als ``BB.uebrige_humusierte`` zu attribuieren  | 
+--------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+   

                                                                                         
Darstellung nicht nach Richtlinie    
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^                                    
Verkehrsinsel sind bei Fussgängerstreifen nicht zu unterbrechen und müssen dementsprechend korrigiert werden.       


Benötigende Layer im QGIS

.. code-block:: none     
                         
   Strasse/ Lagekontrolle 

Beispiele:                            
                                                                                                                       
                                                                                    
.. _Verkehrsinsel_Fussgaengerstreifen:                                              
                                                                                    
.. figure:: _static/Strasse_Verkehrsinsel_Fussgaengerstreifen.png                           
   :width: 550px                                                                    
   :target: _static/Strasse_Verkehrsinsel_Fussgaengerstreifen.png                           
                                                                                    
   ``BB.Verkehrsinsel`` ist beim Fussgängersteifen **nicht** zu unterteilen
                                                                                       

EO.Lärmschutzwand               
-----------------

.. index:: Lärmschutzwand


????? wirklich machen??????


Objekt feht
^^^^^^^^^^^
Ist auf dem aktuellen Orthofoto eine Lärmschutzwand zuerkennen, die nicht in der AV erfasst ist, muss überprüft werden, ob sie die Aufnahmekriterien gemäss *Handbuches der amtlichen Vermessung Kanton Solothurn* erfüllt. Falls dies der Fall ist, ist die Lärmschutzwand terrestrisch zu erfassen.
                                                                                                   
.. note::
   Lärmschutzwände sind über die laufende Nachführung abzurechnen   
   
Benötigende Layer im QGIS

.. code-block:: none     
                         
   Strasse/ Lagekontrolle   

Objekt löschen/ umattribuieren  
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Falls in der AV eine Lärmschutzwand vorhanden ist, welche auf dem aktuellen Orthofoto nicht mehr zu erkennen ist, ist dieses Objekt zu löschen. Ist die Lärmschutzwand in der AV als ``EO.Mauer`` erfasst, ist das Objekt auf "EO.Lärmschutzwand" umzuattribuieren.   

Benötigende Layer im QGIS:: 
    
    Strasse/ Lagekontrolle 
    Hinweis:Lärmschutzwände sind auf dem Orthofoto durch ihren Schattenwurf zu erkennen.       
       

EO.Tunnel_Unterführung_Galerie 
------------------------------
.. index:: Tunnel, Unterführung, Galerie  

Lagekontrolle             
^^^^^^^^^^^^^                                                                                                                                                                 
Wird lediglich durch eine Plausibilitätsprüfung (z.B. Treffen die Geometrien ``BB.Strasse_Weg`` und ``EO.Tunnel_Unterführung_Galerie`` aufeinander) kontrolliert. Die Lage wird jeweils nicht mittels einer Feldkontrolle kontrolliert. Korrekturen in der Lage werden im Rahmen der PNF/Homogenisierung demnach selten bis nie durchgeführt. 

Benötigende Layer im QGIS::
    
    Strasse/ Lagekontrolle 

Objekt feht   
^^^^^^^^^^^                  
Falls ``BB.Strasse_Weg`` durch einen Tunnel, Galerie oder Unterführung unterbrochen wird, darf das ``EO.Tunnel_Unterführung_Galerie`` nicht fehlen.    

Darstellung nicht nach Richtlinie    
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^   
Falls in der AV  nicht jede Röhre des Tunnels Einzel dargestellt ist, wird dies im Rahmen der PNF/Homogenisierung **nicht** korrigiert.     

Benötigende Layer im QGIS::
    
    Strasse/ Lagekontrolle 

EO.Pfeiler    
----------
.. index:: Pfeiler
Lagekontrolle             
^^^^^^^^^^^^^                                                                                                                                                                 
Wird lediglich durch eine Plausibilitätsprüfung (z.B. Liegen die Pfeiler innerhalb der ``EO.Brücke_Passerelle``) kontrolliert. Die Lage wird jeweils nicht mittels einer Feldkontrolle kontrolliert. Korrekturen in der Lage werden im Rahmen der PNF/Homogenisierung demanch selten bis nie durchgeführt.       

Benötigende Layer im QGIS::
    
    Strasse/ Lagekontrolle 

Objekt löschen   
^^^^^^^^^^^^^^    
Pfeiler mit einer Seitenlänge < 50cm sind aus der AV zu löschen      
                                 

Benötigende Layer im QGIS::
    
    Strasse/ Lagekontrolle                                                      
    Strasse/Checklayer/Pfeiler<0.25m2                 
                                                    
EO.Brücke_Passerelle                                   
--------------------
.. index:: Brücke, Passerelle
Lagekontrolle  
^^^^^^^^^^^^^ 
Wird lediglich durch eine Plausibilitätsprüfung kontrolliert. Die Lage wird jeweils nicht mittels einer Feldkontrolle kontrolliert. Korrekturen in der Lage werden im Rahmen der PNF/Homogenisierung demnach selten bis nie durchgeführt. 

 
Objekt fehlt/umattribuieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Fehlende Objekte sind zu erfassen gemäss *Handbuches der amtlichen Vermessung Kanton Solothurn*. Falls die Brücke/Passerelle falsch attribuiert ist, ist dies entsprechend zu korrigieren.       
                                         
EO.schmaler_Weg
---------------   

.. index:: Weg, Wanderweg

Lagekontrolle 
^^^^^^^^^^^^^ 
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) detektiert so ist das Objekt in der AV zu korrigieren. 
Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst. Bei den Wanderwege, die ihren Verlauf jährlich ändern (Graswege) ist keine Korrektur vorzunehmen.
     

Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle   
                                

Beispiele:
                                                                                                                                                            
+----------------------------------------------------------------------------+-----------------------------------------------------------------------+       
|.. _Strasse_schmaler_weg:                                                   |.. _Lagedifferenz_schmaler_Weg:                                        |       
|                                                                            |                                                                       |       
|.. figure:: _static/Strasse_schmaler_weg.png                                |.. figure:: _static/Strasse_Lagedifferenz_schmaler_Weg.png             |       
|   :width: 550px                                                            |   :width: 550px                                                       |       
|   :target: _static/Strasse_schmaler_weg.png                                |   :target: _static/Strasse_Lagedifferenz_schmaler_Weg.png             |       
|                                                                            |                                                                       |       
|   ``EO.schmaler_Weg`` ist **nicht** zu korrigieren, weil auf dem Orthofoto |   ``EO.schmaler_Weg`` ist zu korrigieren, weil die Lagedifferenz      |       
|   der Verlauf nicht klar ersichtlich ist.                                  |   grösser als die Toleranz (TS4: 1.5m) ist und weil der Verlauf auf   | 
|									     |   dem Orthofoto klar zu erkennen ist.                                 |              
+----------------------------------------------------------------------------+-----------------------------------------------------------------------+       
                                                                                                                                                               

                                                                                        
Objekt fehlt/Löschen  
^^^^^^^^^^^^^^^^^^^^
Ist ein Wanderweg im Layer `Wanderwege` vorhanden der nicht in der AV erfasst ist, ist dieser im Rahmen der PNF/Homogenisierung neu ab dem Orthofoto zu digitalisieren. Es werden nur offizielle Wanderwege neu erfasst. 
Wanderwege dürfen nicht unterbrochen sein. Das heisst Wanderwege sind auch darzustellen, wenn sie im Feld nicht ersichtlich sind (z.B. bei Graswegen). Falls Wanderwege in der AV vorhanden sind, die nicht mehr existieren, werden diese gelöscht. 


Benötigende Layer im QGIS:
                                                                                                                                                         
.. code-block:: none

   Strasse/ Lagekontrolle
   


Objekt umattribieren
^^^^^^^^^^^^^^^^^^^^                                                                                                                                                                                                                            
Sind im TS2 ``EO.schmaler_Weg`` erfasst, sind diese neu als ``BB.Strasse_Weg`` zu erfassen. Fusswege im TS2, sind immer der Bodenbedeckung (``BB.Strasse/Weg``) zuzuweisen.

                                                                                                                                                                                                                                                                                                                                     
Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Checklayer/EO.schmaler_Weg in TS 2   
              

EO.Fahrspur                     
----------- 
.. index:: Fahrspuren

Lagekontrolle 
^^^^^^^^^^^^^
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) detektiert so ist das Objekt in der AV zu korrigieren. 
Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst. Ist der Verlauf auf dem Orthofoto nicht klar ersichtlich, ist keine Korrektur vorzunehmen. 


Objekt fehlt/Löschen  
^^^^^^^^^^^^^^^^^^^^
**Neu Fahrspuren werden im Rahmen der PNF/Homogenisierung nicht erhoben**. ``EO.Fahrspuren`` die nicht mehr existieren sind zu löschen. Für die Kontrolle ob eine Fahrspur noch existiert kann eine Feldkontolle sinnvoll sein. 

Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle   
                                

Beispiele:
              
+--------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+
|.. _Strasse_Fahrspur_fehlt:                                                           | .. _Strasse_Fahrspur_loeschen:                                                        |
|                                                                                      |                                                                                       |                                                                                                   
|.. figure:: _static/Strasse_Fahrspur_fehlt.png                                        | .. figure:: _static/Strasse_Fahrspur_loeschen.png                                     |
|   :width: 550px                                                                      |    :width: 550px                                                                      |
|   :target: _static/Strasse_Fahrspur_fehlt.png                                        |    :target: _static/Strasse_Fahrspur_loeschen.png                                     |                              
|                                                                                      |                                                                                       |
|   ``EO.Fahrspur`` wird **nicht** erfasst.                                            |    ``EO.Fahrspur`` ist zu löschen.                                                    |
|                                                                                      |                                                                                       |
+--------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+ 
                                                                                 
           

Objekt umattribieren
^^^^^^^^^^^^^^^^^^^^                                                                                                                                                                                                                            
Befestigte ``EO.Fahrspuren`` sind in ``BB.Strasse_Weg`` und ``EO.Fahrspuren`` die als Fusswege genutzt werden sind in ``EO.schmaler_Weg`` umzuattribuieren.
                                                                                                                                                                                                                                                                                                                                     
Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle   
   
Beispiele:                            
                                                                                                                       
+--------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------+                                                                                 
|.. _Strasse_Fahrspur_umattribuieren:                                                  | .. _Strasse_Fahrspur_umattribuieren_korr:                                               | 
|                                                                                      |                                                                                         | 
|.. figure:: _static/Strasse_Fahrspur_umattribuieren.png                               | .. figure:: _static/Strasse_Fahrspur_umattribuieren_korr.png                            | 
|   :width: 550px                                                                      |    :width: 550px                                                                        | 
|   :target: _static/Strasse_Fahrspur_umattribuieren.png                               |    :target: _static/Strasse_Fahrspur_umattribuieren_korr.png                            | 
|                                                                                      |                                                                                         | 
|   ``EO.Fahrspur`` ist in ``EO.schmaler_Weg`` umzuattribuieren                        |    ``EO.schmaler_Weg`` ist aus der Geometrie ``EO.Fahrspur`` zu konstruieren...??? oder | 
|                                                                                      |    ab dem Orthofoto zu digitalisieren????                                               |
+--------------------------------------------------------------------------------------+-----------------------------------------------------------------------------------------+ 
                                                                                                                                                        

