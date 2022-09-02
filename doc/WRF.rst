Vad är WRF-modellen
===================
- Weather Research & Forecasting
- Utvecklad på NCAR
- Forskning: klimat och modellfysik
- Prognoser: används av vissa vädertjänster
  - Försvaret (METOCC)
- Icke-hydrostatisk: 
-   bra i bergsterräng och konvektionsupplösning
- Exempel på ihopkopplingar
  - vågmodell, havsmodell
- Utbytbar fysik, kan anpassas till ”klimatet” och modellupplösning
- Ideala fall eller reella fall
- Dynamisk nedskalning i flera domäner 
- Open-source och fri programvara
- https://www2.mmm.ucar.edu/wrf/users/ 

WRF
---

Grafiskt schema

WPS
---
- För riktiga prognoser (real) krävs för-processering.
- Geografisk information
  - Geogrid	skapar det rutnät du definierar + landanvändning och topografi
  - Förvalda data är USGS topografi & MODIS landanvändning
  - Egna data
    - Corine-data över Europa landanvändning mycket bättre.
    - Lantmäteriets topografi (METRIA) kan vara viktigt vid högupplösta simuleringar
- Meteorologisk drivning
  - Hämta hem drivdata (GRIB-format). 
  - GFS från NCEP är gratis. 
  - ECMWF innebär kostnad om man inte tillhör akademin. 
  - Finns även databaser för vattentemp/is
Ungrib 	konverterar GRIB till ”intermediate format” 
Metgrid 	sammanför geodata och meteorologisk data i rätt rutnät i gemensamma filer: met_em.d<domän-nummer>.<tidpunkt>

Verkligt fall
-------------

- REAL
  - Interpolerar met-filerna till de vertikala nivåerna som man definierat 
  - ger initialvärden
  - Skapar randdata som förändras för hela prognoslängden.
- WRF
  - Gör själva prognosen genom att stega fram i tid med alla fysikaliska och dynamiska ekvationerna i ett 3d-nät

Att köra WRF-modellen
---------------------
- Datorkraft, åtminstone för 3D
- UNIX/Linux-miljö 
- MacOS fungerar om du har snabb dator
- Cygwin i Windows
  - https://www2.mmm.ucar.edu/wrf/WG2/WRF_Win64.htm
  - Någon med erfarenhet?


