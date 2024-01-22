Installera WRF
==============

För Raspberry Pi
https://github.com/DevinSmoot/HPC-Guides/blob/master/raspi_wrf_guide.md
Finns nyare versioner av WRF och biblioteken, så ta dem!
Annars: https://www2.mmm.ucar.edu/wrf/OnLineTutorial/Introduction/start.php 





Förberedande installationer
---------------------------

Installera bibliotek
fortran, c och c++ kompilatorer
GNU är definitivt gratis
Möjligen kan ni få till INTEL på x86-baserad CPU
Csh shell, perl 
NETCDF-4.1.3 – säkrast välja denna version!
zlib, Openmpi (mpich i instruktion kan bytas ut)
Libpng, JasPer, HDF5, m4 – för GRIB-läsning

Installera WRF
--------------

Ladda hem
https://www2.mmm.ucar.edu/wrf/users/download/get_source.html 
Konfigurera för arm-processor
Välj vilken form av parallellisering, om någon
Serial	bara en ”tråd”, passar 1 till 2-D idealiserade körningar
Smpar	inom en nod, trådar delar på RAM-minnet
Välj bara denna om du kör på en multicore-dator
Dmpar	distribuerat minne, kan både köras inom en nod och över flera noder
dm+sm	kan kombinera parallelliseringsmetoderna
kan vara det effektivaste om man skräddarsyr hur domänen delas upp.
Tar storleksordningen timme att kompilera

.. figure:: images/ideal.png
  :width: 400
  :alt: compile the WRF version of choice


Installera WPS
--------------

För riktiga prognoser (real) krävs förprocessering.
Konfigurera för ditt system
Bygg/kompilera!
Ladda hem geografisk data, flera GB.
