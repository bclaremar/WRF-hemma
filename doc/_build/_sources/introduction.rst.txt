
Introduktion
============

.. note::
   Här tänkte jag samla lite matnyttigt kring hur du sätter upp dina egna väderprognoser.
   
   - Här nedan radar jag upp först upp delarna och stegen som behövs eller kan behövas för att kunna köra en egen väderprognosmodell. 
   - Ibland finns lite olika alternativ beroende vad du redan kan eller har för utrustning.
   - Jag har valt modellen WRF, som jag har mest erfarenhet av, och som amatörer över världen använder.
   - WRF-modellen (då med dataassimilering) används också av många nationella vädertjänster.

   - Längre ner ger jag länkar till online-handledningar eller kortkurser. 
   - Om du är intresserad av att komma igång och du inte vet något om LINUX, eller behöver fräscha upp minnet så föreslår jag att du klickar på en sådan länk innan föredraget. 
   - Titta på första punkten för att bestämma dig för vilket system som passar där. 
   - Under andra punkten är det bra att bestämma vilket system du vill öva dina färdigheter i Linux och sedan eventuellt det system du vill installera WRF i.


Steg
----------


1. Utrustning

  - alt 1: En riktigt snabb dator
  - alt 2a: flera datorer med liknande prestanda i ett ”datorkluster”
  - alt 3b: flera enkortsdatorer, typ RaspberryPi, i ett ”datorkluster”
    
2. Linux eller andra UNIX-liknande system
  
  - Linux på Windows (WSL2)
  - MacOS terminal
  - Linux terminal

3. Installation av WRF och nödvändig sekundär programvara/bibliotek

  - Du behöver kunna läsa filer i NetCDF- och GRIB2-format
  - Om du kör flera datorer behöver du parallelliseringsbiblioteket openMPI
 
4.  Köra WRF

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
