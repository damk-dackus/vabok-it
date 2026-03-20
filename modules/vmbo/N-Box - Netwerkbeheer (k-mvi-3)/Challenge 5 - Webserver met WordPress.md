Challenge 5 – Webserver met WordPress
=====================================

In deze Challenge installeer je een **webserver met WordPress** op het Ubuntu‑werkstation van je groep. Je werkt samen in een groepje. De website die je maakt is via het netwerk bereikbaar voor andere computers in het lokaal. Op de website presenteer je alle groepsleden: wie zitten er in de groep, wat zijn hun hobby’s, interesses en andere zaken.


## AI gebruiken bij deze opdracht

Je mag **AI** (zoals ChatGPT, Copilot of een andere chatbot) gebruiken om deze opdracht te maken. Hier zijn handige manieren:

- **Installatie‑commando’s**: Vraag aan de AI: *"Welke commando’s heb ik nodig om WordPress met Apache en MySQL op Ubuntu te installeren?"* of *"Hoe maak ik een database aan voor WordPress in MySQL?"* De AI geeft je de stappen. Voer ze uit en controleer of het werkt.
- **Foutmeldingen oplossen**: Krijg je een fout? Kopieer de foutmelding en vraag: *"Ik krijg deze fout bij het installeren van WordPress op Ubuntu: [plak de fout]. Wat moet ik doen?"*
- **Firewall instellen**: Vraag bijvoorbeeld: *"Hoe open ik poort 80 in de firewall van Ubuntu met ufw?"*
- **Teksten voor de website**: Vraag de AI om een korte introductietekst voor jullie groep of om tips voor een goede pagina over een groepslid. **Pas de tekst altijd aan** met jullie eigen informatie: echte namen, hobby’s en interesses. De inhoud moet over jullie groep gaan.
- **WordPress uitleg**: Vraag: *"Hoe maak ik een nieuwe pagina in WordPress?"* of *"Hoe voeg ik een bericht toe aan de homepage?"*

**Let op:** AI is een hulpmiddel. Je moet zelf begrijpen wat je doet en de commando’s zelf uitvoeren. Als je iets niet snapt, vraag het aan je docent of zoek het op. De AI kan soms fouten maken; controleer altijd of het resultaat klopt.


## Eindproduct

**Je levert screenshots in van de WordPress‑website.**

In deze screenshots:

- **Laat je zien** dat de website via het netwerk bereikbaar is (vanaf een andere computer in het lokaal).
- **Toon je** de homepage van de website met een korte introductie van jullie groep.
- **Toon je** voor elk groepslid een pagina of bericht met: naam, hobby’s, interesses en andere informatie die jullie willen delen.

Je levert de screenshots in volgens de instructies van je docent (bijvoorbeeld via NNNext of de ELO).


## Deel 1 – Webserver en WordPress installeren op Ubuntu

1. Zorg dat **Ubuntu** op het werkstation draait (bijvoorbeeld via dual boot of als enige besturingssysteem).
2. Installeer een **webserver** (bijvoorbeeld Apache of Nginx), **PHP** en **MySQL** (of MariaDB).
   - Je docent geeft aan welke pakketten je moet installeren.
   - Vaak kun je dit doen met één commando of een installatiescript (bijvoorbeeld LAMP‑stack).
3. Download **WordPress** van wordpress.org en plaats de bestanden in de juiste map van de webserver (bijvoorbeeld `/var/www/html`).
4. Maak een **database** aan voor WordPress (via MySQL of phpMyAdmin).
5. Start de **WordPress‑installatie** in de browser (op het adres van je werkstation, bijvoorbeeld `http://192.168.1.10` of `http://localhost`).
6. Volg de stappen op het scherm: kies een taal, vul de gegevens van de database in, maak een gebruikersnaam en wachtwoord aan voor de beheerder.
7. Controleer of WordPress goed werkt op het werkstation zelf.

> **Tip:** Schrijf het IP‑adres van het werkstation op. Andere computers hebben dit adres nodig om de website via het netwerk te bereiken.


## Deel 2 – Website bereikbaar maken via het netwerk

1. Controleer of het werkstation is aangesloten op het netwerk (via de router of het schoolnetwerk).
2. Zorg dat de **firewall** van Ubuntu de webserver toestaat (poort 80 voor HTTP).
   - Je docent kan uitleggen hoe je dit doet.
3. Test of de website bereikbaar is vanaf **een andere computer** in het lokaal:
   - Open een webbrowser op die computer.
   - Typ het IP‑adres van het werkstation in de adresbalk (bijvoorbeeld `http://192.168.1.10`).
   - De WordPress‑website zou nu moeten verschijnen.
4. Als het niet werkt: controleer het IP‑adres, de netwerkverbinding en de firewall‑instellingen.


## Deel 3 – Website vullen met groepsleden

1. Log in op het **WordPress‑beheerpaneel** (dashboard) van jullie website.
2. Maak een **homepage** of een **bericht** waarin jullie groep zich kort voorstelt (bijvoorbeeld: "Welkom op de website van groep X").
3. Maak voor **elk groepslid** een pagina of bericht met:
   - **Naam** van het groepslid;
   - **Hobby’s** (wat doet hij of zij graag in de vrije tijd?);
   - **Interesses** (waar is hij of zij in geïnteresseerd?);
   - **Andere informatie** die jullie willen delen (bijvoorbeeld favoriete game, sport, muziek).
4. Zorg dat de pagina’s of berichten goed leesbaar zijn en er netjes uitzien.
5. Controleer of alles goed werkt als je de website opent vanaf een andere computer.


## Deel 4 – Screenshots maken en inleveren

1. Open de website vanaf **een andere computer** in het netwerk (niet vanaf het werkstation zelf waar WordPress draait).
2. Maak **screenshots** van:
   - de **homepage** (of de hoofdpagina waar de groep zich voorstelt);
   - de **pagina of het bericht van elk groepslid** (met naam, hobby’s, interesses);
   - eventueel een screenshot waaruit blijkt dat de website via het netwerk bereikbaar is (bijvoorbeeld de adresbalk met het IP‑adres).
3. Sla de screenshots op met duidelijke bestandsnamen (bijvoorbeeld `Homepage.png`, `Groepslid_Jan.png`).
4. Lever de screenshots in volgens de instructies van je docent (bijvoorbeeld via NNNext of de ELO).


## Stappenplan in één overzicht

Gebruik onderstaand stappenplan als leidraad. Je mag hiervan afwijken (zie verderop bij *Eigen aanpak mag ook!*), maar zorg dat alle onderdelen uiteindelijk gedaan zijn.

| Stap | Wat doe je?                                                                                   | Voor in de screenshots                                                                     |
|------|-----------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------|
| 1    | Installeer de webserver, PHP en MySQL (of MariaDB) op Ubuntu.                                 | Niet nodig; dit doe je vooraf.                                                             |
| 2    | Download WordPress en installeer het via de browser.                                         | Niet nodig; dit doe je vooraf.                                                             |
| 3    | Stel de firewall in zodat de website via het netwerk bereikbaar is.                          | Niet nodig; dit doe je vooraf.                                                             |
| 4    | Test of de website bereikbaar is vanaf een andere computer in het netwerk.                   | Screenshot van de website met het IP‑adres in de adresbalk.                                |
| 5    | Maak een homepage of bericht met een korte introductie van jullie groep.                     | Screenshot van de homepage.                                                                |
| 6    | Maak voor elk groepslid een pagina of bericht met naam, hobby’s en interesses.               | Screenshot van elke groepsledenpagina.                                                     |
| 7    | Controleer of alles goed werkt en ziet er netjes uit.                                        | Controleer of alle screenshots compleet zijn.                                              |
| 8    | Lever de screenshots in volgens de instructies van je docent.                               | Controleer of alle bestanden goed zijn opgeslagen en de namen duidelijk zijn.              |


## Eigen aanpak mag ook!

Dit stappenplan helpt je op weg, maar je hoeft het niet precies zo te doen. Misschien werk jij liever in een andere volgorde, of gebruik je een andere manier om WordPress te installeren (bijvoorbeeld met Docker of een ander hulpmiddel). Dat is prima!

**Belangrijk is dat:**

- de **webserver met WordPress** goed draait op het Ubuntu‑werkstation;
- de website **via het netwerk bereikbaar** is vanaf andere computers;
- de website **alle groepsleden** presenteert met naam, hobby’s en interesses;
- je **screenshots** inlevert van de homepage en van elke groepsledenpagina;
- de screenshots laten zien dat de website **via het netwerk** (niet alleen lokaal) bereikbaar is.


## Beoordeling – Rubric Webserver met WordPress

Je docent gebruikt onderstaande rubric om jullie werk te beoordelen.

| Aspect                         | 0 punten (onvoldoende)                                                       | 1 punt (voldoende)                                                                 | 2 punten (goed)                                                                                          |
|--------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------|
| Webserver en WordPress         | WordPress werkt niet of is niet geïnstalleerd.                               | WordPress werkt, maar de installatie was met veel hulp of er zijn fouten.         | WordPress draait goed op Ubuntu; installatie is zelfstandig of met weinig hulp gedaan.                    |
| Bereikbaar via netwerk         | Website is niet bereikbaar vanaf andere computers.                          | Website is soms bereikbaar of alleen lokaal.                                       | Website is goed bereikbaar vanaf andere computers in het netwerk.                                        |
| Inhoud en screenshots          | Website is leeg of screenshots ontbreken; groepsleden niet gepresenteerd.   | Enkele groepsleden ontbreken of screenshots zijn onvolledig.                       | Alle groepsleden zijn gepresenteerd met naam, hobby’s en interesses; screenshots zijn compleet en duidelijk. |

**Beoordeling:**

- **Maximumscore**: 6 punten  
- **Suggestie normering**:  
  - 5–6 punten: goed  
  - 3–4 punten: voldoende  
  - 0–2 punten: onvoldoende


## Inleveren

Ben je klaar met de opdracht?

1. Laat de docent zien dat de website via het netwerk bereikbaar is (open de website vanaf een andere computer).  
2. Lever de **screenshots** van de WordPress‑website in volgens de afspraken (bijvoorbeeld via NNNext of de ELO).  

Pas als beide stappen gedaan zijn, is Challenge 5 volledig afgerond.
