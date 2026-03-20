Challenge 9 – Kennismaking met cybersecurity
===========================================

In deze Challenge maak je kennis met **cybersecurity**: hoe je gegevens veilig houdt. Je krijgt een opdracht van een bedrijf met **personeelsgegevens**. Die gegevens zijn gevoelig. Ze mogen niet zomaar door iedereen bekeken worden. Tegelijk moeten werknemers wel **samen kunnen werken** en bestanden kunnen delen.

Je voert deze opdracht uit op een **Windows Server 2025** die als **fileserver** dient. Daarvoor installeer je eerst **Windows Server 2025** op een **apart werkstation** dat als server wordt gebruikt. Op die server zet je de mappen en rechten voor het bedrijf.


## Het bedrijf (scenario)

Jij werkt voor **Zuydstad Zorgdiensten B.V.** Dit bedrijf regelt planning en administratie voor zorgmedewerkers. Het bedrijf werkt met:

- personeelsgegevens (namen, adressen, geboortedata)
- contracten en urenregistratie
- looninformatie

### De 8 werknemers

Deze 8 werknemers werken samen en delen bestanden:

1. **Fatima de Vries** – HR‑medewerker (contracten, dossiers)
2. **Jasper Smit** – HR‑medewerker (instroom/uitstroom, formulieren)
3. **Sanne Bakker** – Planner (roosters, uren)
4. **Yassin El Amrani** – Planner (roosters, uren)
5. **Lotte van Dijk** – Financieel medewerker (facturen, salarisoverzicht)
6. **Milan Jansen** – Teamleider (overzichten, goedkeuringen)
7. **Romy Peters** – Directie (inzage in rapportages, beslissingen)
8. **Daan Meijer** – IT‑beheerder (beheer, back‑ups, rechten)


## Eindproduct

**Je levert een kort beveiligingsverslag in met screenshots.**

In dit verslag:

- **laat je een mappenstructuur zien** (welke mappen bestaan er voor dit bedrijf);
- **laat je zien wie toegang heeft** tot welke map (rechten/permissions);
- **laat je zien dat samenwerking nog kan** (medewerkers kunnen bij de juiste gedeelde map);
- **laat je zien dat gevoelige mappen beschermd zijn** (niet iedereen kan erbij);
- **voeg je een korte uitleg toe** (in 2F‑taal) waarom je dit zo hebt ingesteld.

Je levert het verslag in als **PDF** of als document volgens de afspraken met je docent.


## Deel 1 – Windows Server 2025 installeren

1. Zorg voor een **apart werkstation** (een aparte computer) dat als **server** gaat dienen. Deze computer wordt niet gebruikt als gewone werkplek, maar alleen om bestanden op te slaan en te delen.
2. Installeer **Windows Server 2025** op dit werkstation.
   - Je docent geeft aan waar je de installatie‑media of het iso‑bestand vandaan haalt.
   - Volg de installatiewizard: kies de juiste taal, partitie en licentie.
   - Geef de server een duidelijke naam (bijvoorbeeld `SRV-ZUIDSTAD` of `Fileserver-Zuydstad`).
3. Na de installatie: stel een **wachtwoord** in voor de beheerder en zorg dat de server op het **netwerk** is aangesloten (via de router of het schoolnetwerk).
4. Controleer of de server goed opstart en of je kunt inloggen.

> **Tip:** Schrijf het IP‑adres van de server op. Andere computers (werkstations van de “werknemers”) hebben dit later nodig om bij de gedeelde mappen te komen.


## Deel 2 – Bestanden en gevoeligheid bepalen

1. Lees het scenario en bedenk welke bestanden het bedrijf gebruikt.
2. Maak een lijst van minimaal deze soorten bestanden (je mag er meer bij verzinnen):
   - **Algemeen** (bijv. bedrijfsregels, handleidingen)
   - **Planning** (roosters, uren)
   - **HR – Dossiers** (contracten, ID‑gegevens, ziekte)
   - **Financiën** (salarisoverzichten, facturen)
   - **Management** (rapportages, beslissingen)
3. Zet erbij welke bestanden **gevoelig** zijn. Bijvoorbeeld:
   - Salaris en HR‑dossiers zijn **heel gevoelig**.
   - Roosters zijn **gevoelig**, maar planners moeten erbij kunnen.
   - Algemene documenten mogen **breed gedeeld** worden.


## Deel 3 – Mappen maken op de Windows Server

1. Log in op de **Windows Server 2025** (op het werkstation dat als server dient).
2. Maak een map aan voor de gedeelde bestanden, bijvoorbeeld op schijf `C:\` of op een aparte gegevensschijf. Noem de map: `Zuydstad_Zorgdiensten`.
3. Maak daarin submappen, bijvoorbeeld:
   - `01_Algemeen`
   - `02_Planning`
   - `03_HR_Dossiers`
   - `04_Financien`
   - `05_Management`
   - `06_IT_Backup` (alleen IT)
4. Bedenk per map: **wie moet erbij kunnen** en wie juist niet.
5. Werk met het idee van **rollen** (groepen) in plaats van losse personen, bijvoorbeeld: HR, Planning, Financiën, Management, IT.

> **Tip:** Met groepen is het overzichtelijker. Als er later een nieuwe werknemer komt, hoef je alleen die persoon aan een groep toe te voegen.


## Deel 4 – Beveiliging instellen op de Windows Server (rechten)

Op de **Windows Server 2025** stel je gebruikers, groepen en rechten in. Zo beveilig je de bestanden, maar kunnen de juiste werknemers nog wel samenwerken.

1. Maak op de server **8 gebruikersaccounts** aan (via Gebruikers en computers of Serverbeheer), voor de 8 werknemers uit het scenario. Je mag afkortingen gebruiken (bijv. f.devries, j.smit).
2. Maak **groepen** (rollen) aan: HR, Planning, Financiën, Management, IT. Voeg de juiste gebruikers aan de juiste groepen toe.
3. Maak de map `Zuydstad_Zorgdiensten` (of de hoofdmap) **gedeeld** (share). Stel **share‑rechten** in zodat alleen aangemelde gebruikers erbij kunnen.
4. Stel per submap **NTFS‑rechten** in (rechtermuisklik op map → Eigenschappen → Beveiliging), zodat:
   - `01_Algemeen`: iedereen (of alle medewerkers) mag lezen; sommige mogen ook wijzigen.
   - `02_Planning`: alleen Planning + Teamleider + Directie.
   - `03_HR_Dossiers`: alleen HR + Directie + IT.
   - `04_Financien`: alleen Financiën + Directie + IT.
   - `05_Management`: Teamleider + Directie (en eventueel lezen voor HR/Financiën).
   - `06_IT_Backup`: alleen IT.
5. Test de rechten vanaf **andere werkstations** (computers in het netwerk):
   - Log in als een planner en ga via het netwerk naar de server (bijv. `\\SRV-ZUIDSTAD\Zuydstad_Zorgdiensten`). Controleer of je **wel** bij `02_Planning` kunt, maar **niet** bij `03_HR_Dossiers`.
   - Log in als HR en test hetzelfde.
   - Maak van elk testmoment een **screenshot**.


## Deel 5 – Extra beveiliging (basis)

Kies minimaal **2** extra beveiligingsmaatregelen en leg kort uit waarom:

- **Sterke wachtwoorden** (minimaal 12 tekens, niet makkelijk te raden)
- **Schermvergrendeling** (automatisch na een paar minuten)
- **Back‑ups** (kopie op andere plek, bijvoorbeeld externe schijf)
- **Versleuteling** (als je docent dit behandelt)
- **Geen admin‑rechten voor iedereen** (alleen IT)


## Stappenplan in één overzicht

Gebruik onderstaand stappenplan als leidraad. Je mag hiervan afwijken (zie verderop bij *Eigen aanpak mag ook!*), maar zorg dat alle onderdelen uiteindelijk gedaan zijn.

| Stap | Wat doe je?                                                                                   | Voor in het verslag                                                                           |
|------|-----------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| 1    | Installeer Windows Server 2025 op een apart werkstation dat als server dient.                 | Screenshot van de server na installatie (bijv. inlogscherm of servernaam).                   |
| 2    | Lees het scenario en bepaal welke bestanden/mappen er zijn.                                   | Lijst van mappen + uitleg welke gevoelig zijn.                                                |
| 3    | Maak op de server de hoofdmap en submappen voor het bedrijf.                                 | Screenshot van de mappenstructuur op de server.                                               |
| 4    | Maak 8 gebruikers en groepen (rollen) op de Windows Server.                                   | Screenshot van gebruikers/groepen.                                                            |
| 5    | Stel gedeelde mappen (share) en NTFS‑rechten in per map.                                     | Screenshot van rechten/permissions per map.                                                   |
| 6    | Test de rechten vanaf andere werkstations (inloggen als verschillende medewerkers).           | Screenshots van geslaagde en geweigerde toegang.                                              |
| 7    | Voeg 2 extra beveiligingsmaatregelen toe en leg uit waarom.                                   | Korte uitleg in 2F + eventueel screenshot.                                                    |
| 8    | Maak het beveiligingsverslag compleet en lever het in.                                         | Verslag (PDF) met alle screenshots en uitleg.                                                 |


## Eigen aanpak mag ook!

Dit stappenplan helpt je op weg, maar je hoeft het niet precies zo te doen. Misschien gebruik je andere mapnamen of een andere indeling. Dat is prima!

**Belangrijk is dat:**

- **Windows Server 2025** is geïnstalleerd op een apart werkstation dat als fileserver dient;
- gevoelige gegevens **niet voor iedereen** toegankelijk zijn;
- werknemers **wel kunnen samenwerken** in de juiste gedeelde mappen op de server;
- je kunt laten zien (met screenshots) dat jouw beveiliging werkt;
- je in eenvoudige zinnen uitlegt **waarom** je deze keuzes maakt.


## Beoordeling – Rubric Cybersecurity (bestanden beveiligen)

Je docent gebruikt onderstaande rubric om jouw werk te beoordelen.

| Aspect                         | 0 punten (onvoldoende)                                                       | 1 punt (voldoende)                                                                 | 2 punten (goed)                                                                                          |
|--------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Server en toegangsrechten      | Server niet geïnstalleerd of rechten kloppen niet; gevoelige mappen voor iedereen open. | Server draait; rechten deels goed, maar met fouten of onduidelijkheden.   | Windows Server 2025 geïnstalleerd op apart werkstation; share- en NTFS-rechten kloppen; gevoelige mappen afgeschermd. |
| Samenwerken                    | Door beveiliging kan bijna niemand samenwerken of alles staat open.          | Samenwerken kan, maar niet overal goed of niet duidelijk getest.                   | Samenwerken werkt goed: juiste groepen hebben toegang vanaf werkstations, en dit is getest.               |
| Verslag en bewijs              | Verslag ontbreekt of heeft weinig bewijs; geen duidelijke screenshots.       | Verslag is aanwezig met enkele screenshots; uitleg soms te kort.                    | Verslag is compleet met duidelijke screenshots en heldere uitleg (2F).                                     |

**Beoordeling:**

- **Maximumscore**: 6 punten  
- **Suggestie normering**:  
  - 5–6 punten: goed  
  - 3–4 punten: voldoende  
  - 0–2 punten: onvoldoende


## Inleveren

Ben je klaar met de opdracht?

1. Controleer of je screenshots duidelijk zijn en of je uitleg klopt.  
2. Lever je beveiligingsverslag in volgens de afspraken (bijvoorbeeld via NNNext of de ELO).  

Pas als dit gedaan is, is Challenge 9 volledig afgerond.

