Strasse
=======
Bei diese Gruppe werden die Stassen der amtlichen Vermessung überprüft auf dessen Vollständigkeit und Richtigkeit in der Lage wie auch in der Darstellung.

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
                         
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) dedektiert so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst. Ist die Lagekontrolle mit dem Orthofoto auf Grund von interpertier Schwierigkeit (z.B. durch Schatten oder Sichthindernisse wie Bäume) nicht möglich kann eine Feldkontolle sinnvoll sein. 

Benötigende Layer im QGIS :: 

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

Benötigende Layer im QGIS :: 

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
                                                                                                                                                                                                                                                                                                                                     
Benötigende Layer im QGIS :: 

  Strasse/ Lagekontrolle   
              

Darstellung nicht nach Richtlinie  
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^  
BB.Strasse_Weg unterbrochen
+++++++++++++++++++++++++++
Das Objekt ``BB.Strasse_Weg`` darf z.B. bei Hofdurchfahrten )oder bei niveaugleichen Kreuzungen nicht unterbrochen sein. Ist dies der Fall, muss dies im Rahmen der PNF/Homogenisierung bereinigt werden. Ziel ist es ein zusammenhängendes Strassen-/Wegnetz zu erhalten . 
Genauere Erläuterung über die Erfassung der Niveauüberggänge sind im *Handbuch der amtlichen Vermessung Kanton Solothurn* zu finden.                 
    
Benötigende Layer im QGIS :: 

   Strasse/ Lagekontrolle 
   Stasse/ Checklayer/ BB.BoFlaeche

BB.Strasse_Weg zu grosses Objekt
++++++++++++++++++++++++++++++++
Grosse Strassenobjekte (>10'000 m2) der ``BB.Strasse_Weg`` sind zu unterteilen.

Benötigende Layer im QGIS :: 

   Stasse/ Checklayer/ BB.Strasse_Weg>10000m2 

BB.Strasse_Weg bei Erschliessung mehrerer Liegenschaften 
++++++++++++++++++++++++++++++++++++++++++++++++++++++++
                                                                                                                                                                                                                                                                       
Strassen und Wege die der Erschliessung mehrerer Liegenschaften oder mehrerer Gebäude dienen, die in der AV als ``BB.GEbäudeerschliessung`` erfasst sind, werden im Rahmen der PNF/Homogenisierung **nicht** korrigiert (siehe :ref:`Beispiel <Strasse_ueber_mehrere_parz>`). 
          

Befestigte Strassenverengungen ohne Höhenunterschied und befahrbarer Teil des Kreisels (Pavé)    
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Befestigte Strassenverengungen ohne Höhenunterschied gehören zu ``BB.Strasse_Weg``. Das selbe gilt für den befahrbarer Teil des Kreisels (Pavé) (siehe :ref:`Beispiel <Strasse_pave>`).                 

Benötigende Layer im QGIS :: 

  Strasse/ Lagekontrolle   

Beispiele:       

+-----------------------------------------------------------------------+---------------------------------------------------------------------------------------+
|.. _Strasse_Hofdurchfahrt:                                             | .. _Strasse_ueber_mehrere_parz:                                                       |
|                                                                       |                                                                                       |                                                                                                   
|.. figure:: _static/Strasse_Hofdurchfahrt.png                          | .. figure:: _static/Strasse_ueber_mehrere_parz.png                                    |
|   :width: 550px                                                       |    :width: 550px                                                                      |
|   :target: _static/Strasse_Hofdurchfahrt.png                          |    :target: _static/Strasse_ueber_mehrere_parz.png                                    |                              
|                                                                       |                                                                                       |
|   ``BB.Strasse_Weg`` draf bei Hofdurchfahrten nicht unterbrochen sein.|    ``BB.Strasse_Weg`` bei Erschliessung mehrerer Liegenschaften wird nicht korrigiert.|                                                                               
|                                                                       |                                                                                       |
+-----------------------------------------------------------------------+---------------------------------------------------------------------------------------+   
|.. _Strasse_pave:                                                      |                                                                                       |
|                                                                       |                                                                                       | 
|.. figure:: _static/Strasse_pave.png                                   |                                                                                       |
|   :width: 550px                                                       |                                                                                       |
|   :target: _static/Strasse_pave.png                                   |                                                                                       |
|                                                                       |                                                                                       |
|   Befahrbarer Teil des Kreisels (Pavé) gehört zu ``BB.Strasse_Weg``.  |                                                                                       | 
|                                                                       |                                                                                       |
+-----------------------------------------------------------------------+---------------------------------------------------------------------------------------+         
                       

BB.Trottoir                                                                 
-----------  

Lagedifferenz  
^^^^^^^^^^^^^
                                                                                                                                                                                 
Wird eine Lagedifferenz zwischen der AV und dem aktuelle Orthofoto grosser als die Toleranz (siehe :ref:`ref_Tz`) dedektiert so ist das Objekt in der AV zu korrigieren. Liegt die Differenz innerhalb der Toleranz wird das Objekt nicht angepasst.

Benötigende Layer im QGIS :: 

   Strasse/ Lagekontrolle   
                                

Beispiele:
                              
+---------------------------------------------------------------------+-----------------------------------------------------------------------+
|.. _Trottoir_Lagedifferenz:                                          |.. _Trottoir_Lagedifferenz_korr:                                       |
|                                                                     |                                                                       |
|.. figure:: _static/Trottoir_Lagedifferenz.png                       |.. figure:: _static/Trottoir_Lagedifferenz_korr.png                    |
|   :width: 550px                                                     |   :width: 550px                                                       |
|   :target: _static/Trottoir_Lagedifferenz.png                       |   :target: _static/Trottoir_Lagedifferenz_korr.png                    |
|                                                                     |                                                                       |
|   ``BB.Trottoir`` ist zu korrigieren, weil die Lagedifferenz        |   ``BB.Trottoir`` ist zu korrigieren gemäss den rot dargestellten     |
|   grösser als die Toleranz (TS2: 0.5m) ist.                         |   Linien.                                                             |
+---------------------------------------------------------------------+-----------------------------------------------------------------------+ 
                                                                                                                                            

Objekt fehlt/Löschen    
^^^^^^^^^^^^^^^^^^^^    

Ist auf dem aktuellen Orthofoto eine Trottoir zu erkennen, nicht in der AV vorhanden ist, ist diese im Rahmen der PNF/Homogenisierung neu zu erfassen. Falls in der AV eine Trottoir vorhanden ist, dass auf dem aktuellen Orthofoto nicht mehr zu erkennen ist, ist dieses Objekt zu löschen oder evtl. einer anderen BB.Art zu zuweisen. 

benötigende Layer im QGIS ::                                                                                                                                                                                                                                                                                                        
                                                                                                                                        
  Strasse/ Lagekontrolle                                                                                                                                                         
  

Objekt umattribieren    
^^^^^^^^^^^^^^^^^^^^  

it dem aktuellen Orthofoto ist zu kontrollieren, ob alle befestigten Strassen und Weg als ``BB.Strasse_Weg`` erfasst sind. Anderfalls müssen die Strassen und Weg umattribuiert werden in ``BB.Strasse_Weg, EO.Fahrspur oder EO.schmaler_Weg``.  
                                                                                                                                                                                                                                                                                            
enötigende Layer im QGIS :: 

 Strasse/ Lagekontrolle   
             

Darstellung nicht nach Richtlinie    
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^                                        











EO.Fahrspur
-----------

EO.schmaler_Weg
---------------
           








.. index:: Stefan, Ziegler

