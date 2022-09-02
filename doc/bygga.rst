Bygga ett datorkluster
======================

Hårdvara
--------
- Datorer eller enkortsdatorer, typ Raspberry Pi — för beräkningsnoderna
  - Alternativa enkortsdatorer: https://itsfoss.com/raspberry-pi-alternatives/
- En dator eller enkortsdator — för master-/login-nod
- Lokala hårddiskar
  - Raspberry Pi: MicroSD-kort per dator, 8-16 GB kan räcka.
- Strömsladdar
  - strömadapter: 5V, 3A, eller USB power supply hub
  - alternativ till enkortdator: Power Over Ethernet (POE), minskar sladdmängd!
- 1x 8-port 10/100/1000 network switch (Gbit switch)
- Ethernetsladdar, eller motsvarande
- En gemensam hårddisk
  - Minst 500 GB men helst 1TB eller mer


Byggandet
---------
- Jag följde denna instruktion
  - Början specifikt för Raspberry Pi
  - https://glmdev.medium.com/building-a-raspberry-pi-cluster-784f0df9afbd
  - Komma igång
    - Installera LINUX och aktivera ssh (fjärråtkomst)
    - Ställ in nätverk mellan noder
    - Delad lagring
     - Installera SLURM jobbschemaläggare
  - Testa lite enklare parallella körningar utan specialkod
    - Installera program på beräkningsnoderna från mastern
  - OpenMPI, Python, parallella jobb
- Följ gärna delarna i slutet också så lär du dig något extra!
- Detta görs bäst i lugn och ro och lite ”trial and error”

Alternativa kopplingar
----------------------
