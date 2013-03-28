Strasse
=======
Bei diese Gruppe werden die Elemente der Stassen aus der amtlichen Vermessung überprüft auf dessen Vollständigkeit und Richtigkeit in der Lage wie auch in der Darstellung.

Folgende Bodenbedeckungsarten und Einzelobjektarten werden heirbei überprüft:

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

Lagedifferenz  
^^^^^^^^^^^^^
                         
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) dedektiert so ist das Objekt in der AV zu korrigieren.                                                 
Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst. Ist die Lagekontrolle mit dem Orthofoto auf Grund von interpertier Schwierigkeit (z.B. durch 
Schatten oder Sichthindernisse wie Bäume) nicht möglich kann eine Feldkontolle sinnvoll sein. 

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
|   ``BB.Strasse_Weg?? ist **nicht** zu korrigieren, weil die         |   ``BB.Strasse_Weg`` ist **nicht** zu korrigieren, weil Lagedifferenz |
|   Lagedifferenz kleiner als die Toleranz (TS3: 1.5 m) ist.          |   kleiner als die Toleranz (TS4: 1.5 m) ist.                          |
+---------------------------------------------------------------------+-----------------------------------------------------------------------+


Objekt fehlt/Löschen  
^^^^^^^^^^^^^^^^^^^^
Ist auf dem aktuellen Orthofoto eine befestigte Strasse/Weg zu erkennen, die nicht als Bodenbedekung oder als Einzelobjekt in der AV vorhanden ist, ist diese im Rahmen der PNF/Homogenisierung neu zu erfassen. 
Ist in der AV eine befestigte Strasse/Weg vorhanden, die auf dem aktuellen Orthofoto nicht mehr zu erkennen ist und auch die Kriterein der ``EO.Fahrspur`` resp. ``EO.schmaler_Weg`` nicht erfüllt, ist dieses Objekt zu löschen. Ebenfalls zu löschen sind private befetigte Gartenwege.

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
|   ``BB.Strasse_Weg`` fehlt. ``BB.Strasse_Weg`` ist zu erfassen      |   ``BB.Strasse_Weg`` ist zu löschen                                   |
+---------------------------------------------------------------------+-----------------------------------------------------------------------+

Objekt umattribieren
^^^^^^^^^^^^^^^^^^^^                                                                                                                                                                                                                            
Mit dem aktuellen Orthofoto ist zu kontrollieren, ob alle befestigten Strassen und Weg als ``BB.Strasse_Weg`` erfasst sind. Anderfalls müssen die Strassen und Weg umattribuiert werden in ``BB.Strasse_Weg, EO.Fahrspur oder EO.schmaler_Weg``.  
                                                                                                                                                                                                                                                                                                                                     
Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle   
              

Darstellung nicht nach Richtlinie  
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^  
BB.Strasse_Weg unterbrochen
+++++++++++++++++++++++++++
Das Objekt ``BB.Strasse_Weg`` darf z.B. bei Hofdurchfahrten oder bei niveaugleichen Kreuzungen nicht unterbrochen sein. Ist dies der Fall, muss dies im Rahmen der PNF/Homogenisierung bereinigt werden. Ziel ist es ein zusammenhängendes Strassen-/Wegnetz zu erhalten . 
Genauere Erläuterung über die Erfassung der Niveauüberggänge sind im *Handbuch der amtlichen Vermessung Kanton Solothurn* zu finden.                 
    
Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle 
   Stasse/ Checklayer/ BB.BoFlaeche

BB.Strasse_Weg zu grosses Objekt
++++++++++++++++++++++++++++++++
Grosse Strassenobjekte (>10'000 m2) der ``BB.Strasse_Weg`` sind zu unterteilen.

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
  
  
Parallele Darstellung innerhalb der Toleranz
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Nicht parallele Darstellungen der ``BB.Strasse_Weg`` werden im Rahmen der PNF/Homogenisierung **nicht** korrigiert.


Durch Felspartien überdeckte Strassen
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^                                                                                                                                                                                        
Bei den Strassen die durch Felspartien überdeckt sind gelten die Darstellungsrichtline gemäss *Handbuch der amtlichen Vermessung Kanton Solothurn*. Unterscheidet sich die Dartsellung in der AV von der von Richtlinie, ist entsprechend zu korigieren.           
                                                                                                                                                                                                                                                             

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
|   Befestigte Strassenverengungen ohne Nievauunterschied gehört zu ``BB.Strasse_Weg``.|    Befahrbarer Teil des Kreisels (Pavé) gehört zu ``BB.Strasse_Weg``.                 | 
|                                                                                      |                                                                                       |
+--------------------------------------------------------------------------------------+---------------------------------------------------------------------------------------+         
                      

BB.Trottoir                                                                 
-----------  

Lagedifferenz  
^^^^^^^^^^^^^
                                                                                                                                                                                 
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) dedektiert so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst.

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

Lagedifferenz  
^^^^^^^^^^^^^
                                                                                                                                                                                 
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) dedektiert so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst.

Benötigende Layer im QGIS:

.. code-block:: none 

   Strasse/ Lagekontrolle   
                                

                                                                                                                                       
Objekt fehlt/löschen     
^^^^^^^^^^^^^^^^^^^^    

Ist auf dem aktuellen Orthofoto eine Verkehrsinsel zu erkennen, die nicht in der AV vorhanden ist, ist diese im Rahmen der PNF/Homogenisierung neu zu erfassen. 
Falls in der AV eine Verkehrsinsel vorhanden ist, welche auf dem aktuellen Orthofoto nicht mehr zu erkennen ist, ist dieses Objekt zu löschen. Ebenfalls zu löschenn sind temporär angelegte Verkehrsinseln oder befestigte Verkehrsinsel ohne Niveauunterschied die in der AV erfasst sind.
 
                                                                                                                                                                                       
Benötigende Layer im QGIS:

.. code-block:: none                                                                                                                                                                                                                                                                                                       
                                                                                                                                        
  Strasse/ Lagekontrolle                                                                                                                                                         
                                                                                                                                                                                                                                                                                        
Objekt umattribieren
^^^^^^^^^^^^^^^^^^^^ 
Verkehrsinsel sind sind komplet von ``BB.Strasse_Weg`` umgeben. Strassenveränegungen die humusiert sind werden als ``BB.uebrige_humusierte`` attribuiert.
Humusierte Trennstreifen z.B. bei Autobahnen oder zwischen Strassen und z.B. Radwegen gehören zur ``BB.uebrige_humusierte`` und **nicht** zu den ``BB.Verkehrsinseln``.

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
|   Humusierte Strassenveränegungen sind als ``BB.uebrige_humusierte`` zu attribuieren |   Humusierte Trenstreifen sind als ``BB.uebrige_humusierte`` zu attribuieren  | 
+--------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+   

                                                                                         
Darstellung nicht nach Richtlinie    
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^                                    
Verkehrsinsel sind bei Fussgängerstreifen nicht zu unterbrechen und müssen dementsprechend korrigiert werden.       


Benötigende Layer im QGIS

.. code-block:: none     
                         
   Strasse/ Lagekontrolle 

Beispiele:                            
                                                                                                                       
                                                                                    
.. _Verkehrsinsel_Fussgaengerstreifen:                                              
                                                                                    
.. figure:: _static/Verkehrsinsel_Fussgaengerstreifen.png                           
   :width: 550px                                                                    
   :target: _static/Verkehrsinsel_Fussgaengerstreifen.png                           
                                                                                    
   ``BB.Verkehrsinsel`` ist beim Fussgängersteifen **nicht** zu unterteilen
                                                                                       

EO.Lärmschutzwand               
-----------------
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

Lagekontrolle             
^^^^^^^^^^^^^                                                                                                                                                                 
Wird lediglich durch eine Plausibilitätsprüfung (z.B. Treffen die Geometrien ``BB.Strasse_Weg`` und ``EO.Tunnel_Unterführung_Galerie`` aufeinander) kontrolliert. Die Lage wird jeweils nicht mittels einer Feldkontrolle kontrolliert. Korrekturen in der Lage werden im Rahmen der PNF/Homogenisierung demanch selten bis nie durchgeführt. 

Benötigende Layer im QGIS::
    
    Strasse/ Lagekontrolle 

Objekt feht   
^^^^^^^^^^^                  
Falls ``BB.Strasse_Weg`` durch einen Tunnel, Galerie oder Unterführung unterbrochen wird, darf das ``EO.Tunnel_Unterführung_Galerie`` nicht fehlen.    

Darstellung nicht nach Richtlinie    
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^   
Falls in der AV  nicht jede Röhre des Tunnels einzel dargestellt ist, wird dies im Rahmen der PNF/Homogenisierung **nicht** korrigiert.     

Benötigende Layer im QGIS::
    
    Strasse/ Lagekontrolle 

EO.Pfeiler    
----------
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
Lagekontrolle  
^^^^^^^^^^^^^ 
Wird lediglich durch eine Plausibilitätsprüfung kontrolliert. Die Lage wird jeweils nicht mittels einer Feldkontrolle kontrolliert. Korrekturen in der Lage werden im Rahmen der PNF/Homogenisierung demanch selten bis nie durchgeführt. 

 
Objekt fehlt/umattribuieren
^^^^^^^^^^^^^^^^^^^^^^^^^^^
Fehlende Objekte sind zu erfassen gemäss *Handbuches der amtlichen Vermessung Kanton Solothurn*. Falls die Brücke/Passerelle falsch attribuiert ist dies entsprechend zu korrigieren.       
                                         
EO.schmaler_Weg
---------------   

Lagekontrolle 
^^^^^^^^^^^^^ 
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) dedektiert so ist das Objekt in der AV zu korrigieren. 
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
|   der Verlauf nicht klar ersichtlich ist.                                  |   grösser als die Toleranz (TS4: 1.5m) ist.                           |       
+----------------------------------------------------------------------------+-----------------------------------------------------------------------+       
                                                                                                                                                               

                                                                                        
Objekt fehlt/Löschen  
^^^^^^^^^^^^^^^^^^^^
Ist auf dem aktuellen Orthofoto eine befestigte Strasse/Weg zu erkennen, die nicht als Bodenbedekung oder als Einzelobjekt in der AV vorhanden ist, ist diese im Rahmen der PNF/Homogenisierung neu zu erfassen. 
Ist in der AV eine befestigte Strasse/Weg vorhanden, die auf dem aktuellen Orthofoto nicht mehr zu erkennen ist und auch die Kriterein der ``EO.Fahrspur`` resp. ``EO.schmaler_Weg`` nicht erfüllt, ist dieses Objekt zu löschen. Ebenfalls zu löschen sind private befetigte Gartenwege.

Benötigende Layer im QGIS:
                                                                                                                                                         
.. code-block:: none

   Strasse/ Lagekontrolle


Beispiele:















Objekt umattribieren
^^^^^^^^^^^^^^^^^^^^                                                                                                                                                                                                                            
Mit dem aktuellen Orthofoto ist zu kontrollieren, ob alle befestigten Strassen und Weg als ``BB.Strasse_Weg`` erfasst sind. Anderfalls müssen die Strassen und Weg umattribuiert werden in ``BB.Strasse_Weg, EO.Fahrspur oder EO.schmaler_Weg``.  
                                                                                                                                                                                                                                                                                                                                     
Benötigende Layer im QGIS:

.. code-block:: none

   Strasse/ Lagekontrolle   
              

Darstellung nicht nach Richtlinie       


EO.Fahrspur                     
-----------                              
                                                 

                                                                                 
           








.. index:: Stefan, Ziegler

