
Introduktion
============

.. Intro::
   Här tänkte vi samla lite matnyttigt kring hur du sätter upp dina egna väderprognoser



Steg
----------


#. Utrustning

  - alt 1: En riktigt snabb dator
  - alt 2a: flera datorer med liknande prestanda i ett ”datorkluster”
  - alt 3b: flera enkortsdatorer, typ RaspberryPi, i ett ”datorkluster”
    
#. Linux eller andra UNIX-liknande system
  
  - Linux på Windows (WSL2)
  - MacOS terminal
  - Linux terminal

#. Installation av WRF och nödvändig sekundär programvara/bibliotek

  - Du behöver kunna läsa filer i NetCDF- och GRIB2-format
  - Om du kör flera datorer behöver du parallelliseringsbiblioteket openMPI
 
#.  Köra WRF

  - Geografisk data
  - Meteorologisk drivning, GFS 0.25° från NCEP är gratis.
  - 3D-version av WRF, eller 1D-version (ej så krävande).

5. Analysera resultatet

  - wrf-python

6. Automatisera (frivilligt men bra om man just kör prognoser)

  - skript och kronjobb

7. Publicera på webben (frivilligt)

  - För egen del sätt upp egen webserver
  - Annars på ”webhotell”
