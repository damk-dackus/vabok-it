# User Story – Examendocumenten achter login (beoordelingsformulier + officiële examenvraag)

**Datum**: 2026-02-10  
**Module/Context**: Afstemmen en Plannen (portfolio / examencontext)  
**Doel**: Functionele beschrijving + testbare acceptatiecriteria voor een nieuwe websitefunctie.

---

## 1. Context en probleem

Binnen de website moeten gebruikers die **ingelogd** zijn, snel de juiste examendocumenten kunnen vinden:

- Het **beoordelingsformulier**
- De **officiële examenvraag**

Zonder inloggen mogen deze documenten niet zichtbaar of toegankelijk zijn.

---

## 2. User story

**Als** ingelogde student/kandidaat  
**wil ik** op de website het bijbehorende beoordelingsformulier én de officiële examenvraag kunnen vinden en openen/downloaden  
**zodat** ik precies weet wat er verwacht wordt en kan werken volgens de officiële eisen.

---

## 3. Scope

### In scope
- Documenten zijn alleen beschikbaar voor **ingelogde** gebruikers.
- Documenten zijn **vindbaar** via een duidelijke pagina/sectie (bijv. “Examendocumenten”).
- Documenten zijn te **openen** (viewer/nieuw tabblad) en/of te **downloaden**.
- Duidelijke meldingen bij **geen toegang** of **niet beschikbaar**.

### Out of scope (nu niet)
- Bewerken/annoteren van documenten in de website.
- Complex rechtenmodel (tenzij al nodig in de website).
- Versiebeheer-workflow voor docenten (uploaden/publiceren) als aparte beheerfunctie.

---

## 4. Functionele en niet-functionele eisen

### 4.1 Functionele eisen (FE)

| ID | Eisen |
|----|--------|
| **FE1.1** | Het systeem controleert bij het openen van de examendocumenten-pagina/sectie of de gebruiker is ingelogd (geldige sessie/token). |
| **FE1.2** | Het systeem toont de examendocumenten-pagina/sectie alleen als de gebruiker is ingelogd. |
| **FE1.3** | Het systeem toont voor niet-ingelogde gebruikers een melding “Log in om examendocumenten te bekijken” en geen documenten. |
| **FE2.1** | Het systeem toont voor ingelogde gebruikers minimaal twee documenten: het beoordelingsformulier en de officiële examenvraag. |
| **FE2.2** | Het systeem biedt per document de mogelijkheid om het document te openen (bijv. in nieuwe tab of viewer). |
| **FE2.3** | Het systeem biedt per document de mogelijkheid om het document te downloaden. |
| **FE3.1** | Het systeem biedt via navigatie (menu of projectpagina) een duidelijke entry naar “Examendocumenten”. |
| **FE4.1** | Het systeem blokkeert directe toegang tot document-URL’s voor niet-ingelogde gebruikers (geen documentinhoud zonder authenticatie). |
| **FE5.1** | Het systeem toont bij ontbreken of niet-beschikbaar zijn van een document de melding “Document tijdelijk niet beschikbaar” in plaats van een kapotte link. |
| **FE5.2** | Indien van toepassing: het systeem toont bij ingelogde gebruikers zonder rechten voor het project/examen de melding “Geen toegang” en geen documenten. |

### 4.2 Niet-functionele eisen (NFE)

| ID | Categorie | Eisen |
|----|-----------|--------|
| **NFE1.1** | **Veiligheid** | Toegang tot examendocumenten mag alleen plaatsvinden na succesvolle authenticatie; document-URL’s zijn niet raadpleegbaar zonder geldige sessie. |
| **NFE1.2** | **Veiligheid** | Documenten worden niet in de frontend geëxposeerd via voorspelbare of ongeautoriseerde URLs (bijv. geen directe bestandspaden zonder autorisatiecheck). |
| **NFE2.1** | **Gebruiksvriendelijkheid** | De pagina/sectie Examendocumenten is binnen maximaal drie klikken bereikbaar vanuit het hoofdmenu of de relevante projectpagina. |
| **NFE2.2** | **Gebruiksvriendelijkheid** | Foutmeldingen (niet ingelogd, geen toegang, document niet beschikbaar) zijn in begrijpelijke taal en consistent geformuleerd. |
| **NFE3.1** | **Prestaties** | De examendocumenten-pagina laadt binnen 3 seconden onder normale omstandigheden; documenten openen/downloaden start binnen 2 seconden na klik. |
| **NFE4.1** | **Beschikbaarheid** | De beschikbaarheid van de examendocumenten-functie volgt de beschikbaarheid van de bestaande login en hoofdsite. |
| **NFE5.1** | **Compatibiliteit** | De functie werkt in dezelfde browsers en op dezelfde apparaten als de rest van de website (desktop en mobiel). |
| **NFE6.1** | **Toegankelijkheid** | Tekst en knoppen op de examendocumenten-pagina voldoen aan dezelfde toegankelijkheidsnormen als de rest van de site (bijv. contrast, focus, leesbaar door screenreaders). |

---

## 5. Acceptatiecriteria (Given / When / Then)

### AC1 – Niet ingelogd: geen toegang
- **Gegeven** dat ik niet ben ingelogd  
  **wanneer** ik de pagina/sectie “Examendocumenten” open  
  **dan** zie ik een melding “Log in om examendocumenten te bekijken”  
  **en** zie ik de documenten niet  
  **en** kan ik de documenten niet openen via directe link/URL.

### AC2 – Ingelogd: documenten zijn zichtbaar
- **Gegeven** dat ik ben ingelogd  
  **wanneer** ik de pagina/sectie “Examendocumenten” open  
  **dan** zie ik minimaal twee items:
  - **Beoordelingsformulier**
  - **Officiële examenvraag**

### AC3 – Vindbaarheid via navigatie
- **Gegeven** dat ik ben ingelogd  
  **wanneer** ik het menu of de relevante project/examenpagina bekijk  
  **dan** is er een duidelijke entry/knop naar “Examendocumenten”.

### AC4 – Openen van documenten
- **Gegeven** dat ik ben ingelogd  
  **wanneer** ik op “Beoordelingsformulier” klik  
  **dan** opent het document zonder foutmelding (bijv. in een nieuwe tab of viewer).

- **Gegeven** dat ik ben ingelogd  
  **wanneer** ik op “Officiële examenvraag” klik  
  **dan** opent het document zonder foutmelding (bijv. in een nieuwe tab of viewer).

### AC5 – Downloaden van documenten
- **Gegeven** dat ik ben ingelogd  
  **wanneer** ik op “Download” klik bij een document  
  **dan** wordt het juiste bestand gedownload met een logische bestandsnaam.

### AC6 – Geen rechten (optioneel, als dit concept bestaat)
- **Gegeven** dat ik ben ingelogd maar geen toegang heb tot dit specifieke project/examen  
  **wanneer** ik “Examendocumenten” open  
  **dan** krijg ik een melding “Geen toegang”  
  **en** kan ik de documenten niet zien of openen.

### AC7 – Document ontbreekt of is niet beschikbaar
- **Gegeven** dat ik ben ingelogd  
  **wanneer** een document ontbreekt of tijdelijk niet beschikbaar is  
  **dan** zie ik een duidelijke melding “Document tijdelijk niet beschikbaar”  
  **en** wordt er geen kapotte link getoond.

---

## 6. Definition of Done (DoD)

De user story is “done” wanneer minimaal het volgende waar is:

### 6.1 Implementatie
- Alle functionele eisen **FE1.1 t/m FE5.2** zijn geïmplementeerd.
- Alle relevante niet-functionele eisen **NFE1.1 t/m NFE6.1** zijn aantoonbaar geborgd (bijv. via configuratie, logging, monitoring of review).

### 6.2 Testen
- Alle acceptatiecriteria **AC1 t/m AC7** zijn succesvol getest (handmatig of geautomatiseerd).
- De belangrijkste scenario’s zijn getest op ten minste één desktopbrowser en één mobiel apparaat.
- Er zijn geen openstaande blocking/critical bugs gerelateerd aan het bekijken of downloaden van examendocumenten.

### 6.3 Beveiliging & toegang
- Niet-ingelogde gebruikers kunnen examendocumenten niet zien én niet openen via directe URL.
- Gebruikers zonder rechten voor het project/examen krijgen geen inhoud te zien en krijgen een duidelijke melding (“Geen toegang”), indien dit concept wordt gebruikt.

### 6.4 UX & content
- De pagina/sectie “Examendocumenten” is via de afgesproken navigatie (menu of projectpagina) te bereiken.
- De teksten voor knoppen en meldingen (“Log in om examendocumenten te bekijken”, “Geen toegang”, “Document tijdelijk niet beschikbaar”) zijn afgestemd met de opdrachtgever/docent.

### 6.5 Documentatie
- Er is kort vastgelegd waar de documenten technisch staan (pad/URL) en hoe nieuwe versies geplaatst moeten worden.
- Deze user story, de eisen en de Definition of Done zijn opgenomen in de projectdocumentatie (dit document).

---

## 7. MoSCoW (prioriteit)

- **Must have**
  - Login vereist voor toegang tot examendocumenten
  - Beoordelingsformulier en officiële examenvraag zichtbaar voor ingelogde gebruiker
  - Openen/downloaden werkt
  - Geen toegang voor niet-ingelogde gebruiker (ook niet via directe link)

- **Should have**
  - Duidelijke navigatie (“Examendocumenten” in menu/onder project)
  - Duidelijke statusmeldingen (geen toegang / niet beschikbaar)
  - Vermelding van versie/datum van documenten

- **Could have**
  - Korte uitleg/tooltip “Waar gebruik je dit voor?”
  - “Laatste update”-datum + changelog

- **Won’t have (nu niet)**
  - Documenten bewerken/annoteren in de website
  - Upload/publiceerflow voor docenten (als aparte beheerfeature)

---

## 8. Notities / aannames

- Documenten zijn bijvoorbeeld **PDF** (of afbeeldingen zoals PNG) en worden centraal beheerd.
- “Ingelogd” betekent: gebruiker heeft een geldige sessie/token via de bestaande login van de website.
- Als er projectcontext is (documenten per project), dan worden de documenten getoond voor het **juiste** project.

