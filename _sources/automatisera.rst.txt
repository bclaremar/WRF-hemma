Automatisera
============

Förenkla för dig!
-----------------

När du ser att modellen fungerar och du får OK prognoser
Skriv skript då du själv slipper göra alla steg manuellt
För en körning måste allt detta göras med rätta tidsperioder satta
Ladda hem lågupplöst meteorologisk data
Ungrib
Metgrid
Real
wrf

Skript
------

Med ett bra skript behöver du bara som argument ge datum och eventuellt nåt mer som du brukar variera.
Ex ./script_WRF.sh 2021 09 28 06 48 2
d.v.s. datum/tid för prognosstart, 48h-prognoslängd och sen antal (fördefinierade domäner)

Om du startar en ny prognos vissa klockslag varje dag kan du programmera skriptet att använda aktuellt klockslag för att veta vilken prognos du ska göra!


Exempel
-------

Antingen skriver man få långa skript som tar hand om allt
Eller, att föredra, ett litet skript i taget
gör sedan ett huvudskript som samlar ihop alla delar
Arbetsflöde för en prognocykel
Download.sh	kan ta flera timmar om du tar globala data
scriptWPS.sh	storleksordning ca 1 timme, 
run_ungrib.sh
run_metgrid
Anropa scriptWRF.sh när det andra är klart
scriptWRF.sh		exempelutdrag strax
Länka met.em-filer
Run_real.sh
Run_ wrf			exempelutdrag strax
Starta sbatch

Huvudskript
###########

#!/bin/bash
# cd till rätt katalog!!!
#fixa rätt start- och sluttid
m=$(date --date="7 hours ago" "+%m")
d=$(date --date="7 hours ago" "+%d")
hh=$(date --date="7 hours ago" "+%k")
...
#Fixar med datum- och tidsformat och får fram starttider
#yys;mms;dds;hhs
#Och sluttider
#yye;mme;dde;hhs
#och antal domäner: doms och lite fysikparametrar
...
./run_real_9km.sh $yys $mms $dds $hhs $yye $mme $dde $hhe $doms $dt $slph $blph $rst $flex
./run_wrf_9km_3km.sh $yys $mms $dds $hhs $yye $mme $dde $hhe $doms $dt $slph $blph $rst $flex

run_wrf
#######

#!/bin/bash
# cd till rätt katalog!!!
#fixa rätt start- och sluttid
m=$(date --date="7 hours ago" "+%m")
d=$(date --date="7 hours ago" "+%d")
hh=$(date --date="7 hours ago" "+%k")
...
#Fixar med datum- och tidsformat och får fram starttider
#yys;mms;dds;hhs
#Och sluttider
#yye;mme;dde;hhs
#och antal domäner: doms och lite fysikparametrar
...
./run_real_9km.sh $yys $mms $dds $hhs $yye $mme $dde $hhe $doms $dt $slph $blph $rst $flex
./run_wrf_9km_3km.sh $yys $mms $dds $hhs $yye $mme $dde $hhe $doms $dt $slph $blph $rst $flex



Kronjobb
---------

Nästa steg är att göra ett kronjobb 
kör skriptet ett bestämt klockslag varje dag eller med visst intervall.
https://en.wikipedia.org/wiki/Cron 
						you need full path! In script as well!
50 17-23/6 * * *  /clusterfs2/WRF/DATA/downloadscript2
50 05 * * *      /clusterfs2/WRF/DATA/downloadscript2
50 11 * * *      /clusterfs2/WRF/DATA/downloadscript48

20 14 * * *      /clusterfs2/WRF/WPS/script_WPS48.sh
20 01-07/6 * * *  /clusterfs2/WRF/WPS/script_WPS24hdom2.sh

50 7-17/6 * * * run/an.sh		#analys
04 21 * * * run/an.sh


