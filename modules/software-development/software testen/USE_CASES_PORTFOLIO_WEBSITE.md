# Use Cases Document
## IT Showcase

**Document Versie:** 1.0  
**Datum:** 2026-01-11  
**Status:** Gepubliceerd  
**Auteur:** Mark Dackus  

---

## Versiehistorie

| Versie | Datum | Auteur | Wijzigingen | Status |
|--------|-------|--------|-------------|--------|
| 1.0 | 2026-01-11 | Mark Dackus | Eerste versie van het Use Cases document. Alle use cases gedefinieerd voor IT Showcase systeem. | Gepubliceerd |

---

## Inhoudsopgave

1. [Inleiding](#1-inleiding)
2. [Actoren](#2-actoren)
3. [Use Cases Authenticatie en Autorisatie](#3-use-cases-authenticatie-en-autorisatie)
4. [Use Cases Projectbeheer](#4-use-cases-projectbeheer)
5. [Use Cases Profielbeheer](#5-use-cases-profielbeheer)
6. [Use Cases Contentweergave](#6-use-cases-contentweergave)
7. [Use Cases Zoeken en Filteren](#7-use-cases-zoeken-en-filteren)
8. [Use Cases Beheerfunctionaliteit](#8-use-cases-beheerfunctionaliteit)

---

## 1. Inleiding

Dit document beschrijft alle use cases voor het IT Showcase systeem. Elke use case beschrijft een specifieke interactie tussen een actor en het systeem. Het Software Requirement Specification (SRS) document is gebaseerd op dit document en beschrijft de functionele eisen die voortvloeien uit deze use cases.

### 1.1 Doel van dit Document

Dit document dient als:
- Referentie voor ontwikkelaars tijdens de implementatie
- Basis voor testcases en testscenario's
- Communicatiemiddel tussen stakeholders
- Documentatie voor toekomstige onderhoud en uitbreidingen

### 1.2 Use Case Structuur

Elke use case bevat de volgende elementen:
- **Use Case ID**: Unieke identificatie (bijvoorbeeld UC1.1)
- **Naam**: Korte beschrijvende naam
- **Actoren**: Wie voert de use case uit
- **Precondities**: Wat moet er al zijn voordat de use case kan worden uitgevoerd
- **Beschrijving**: Korte beschrijving van wat de use case doet
- **Belangrijke stappen**: De hoofdstroom van de use case
- **Alternatieve flows**: Wat gebeurt er als er iets misgaat of afwijkt
- **Postcondities**: Wat is het resultaat na het uitvoeren van de use case
- **Gerelateerde Requirements**: Verwijzing naar de functionele eisen uit het SRS

---

## 2. Actoren

Het systeem kent de volgende actoren:

- **Bezoeker**: Een niet-ingelogde gebruiker die de website bezoekt
- **Student**: Een ingelogde student die projecten en profiel kan beheren
- **Docent**: Een ingelogde docent die projecten kan beoordelen en goedkeuren
- **Beheerder**: Een ingelogde beheerder met volledige toegang tot alle functionaliteit
- **Systeem**: Het IT Showcase systeem zelf

---

## 3. Use Cases Authenticatie en Autorisatie

### UC1.1: Gebruikersaccount aanmaken

**Actoren:** Beheerder  
**Precondities:** 
- Beheerder is ingelogd
- Beheerder heeft rechten om accounts aan te maken

**Beschrijving:**  
Een beheerder maakt een nieuw gebruikersaccount aan voor een student, docent of andere beheerder.

**Belangrijke stappen:**
1. Beheerder navigeert naar de gebruikersbeheer pagina
2. Beheerder klikt op "Nieuw account aanmaken"
3. Systeem toont het account aanmaakformulier
4. Beheerder vult in:
   - Voornaam
   - Achternaam
   - E-mailadres
   - Wachtwoord
   - Gebruikersrol (Student, Docent, Beheerder)
5. Beheerder klikt op "Account aanmaken"
6. Systeem valideert de invoer:
   - E-mailadres is uniek en heeft geldig formaat
   - Wachtwoord voldoet aan eisen (minimaal 8 karakters, combinatie letters en cijfers)
7. Systeem maakt het account aan
8. Systeem stuurt een welkomstmail met inloggegevens naar de nieuwe gebruiker
9. Systeem toont bevestigingsmelding aan beheerder

**Alternatieve flows:**

**A1: E-mailadres bestaat al**
- 6a. Systeem detecteert dat e-mailadres al bestaat
- 6b. Systeem toont foutmelding: "Dit e-mailadres is al in gebruik"
- 6c. Gebruiker kan e-mailadres aanpassen en opnieuw proberen
- Flow gaat terug naar stap 4

**A2: Ongeldig e-mailformaat**
- 6a. Systeem detecteert ongeldig e-mailformaat
- 6b. Systeem toont foutmelding: "Ongeldig e-mailformaat"
- 6c. Gebruiker kan e-mailadres aanpassen en opnieuw proberen
- Flow gaat terug naar stap 4

**A3: Wachtwoord voldoet niet aan eisen**
- 6a. Systeem detecteert dat wachtwoord niet voldoet aan eisen
- 6b. Systeem toont foutmelding: "Wachtwoord moet minimaal 8 karakters bevatten en een combinatie van letters en cijfers zijn"
- 6c. Gebruiker kan wachtwoord aanpassen en opnieuw proberen
- Flow gaat terug naar stap 4

**Postcondities:**
- Nieuw gebruikersaccount is aangemaakt in het systeem
- Welkomstmail is verstuurd naar de nieuwe gebruiker
- Beheerder ziet bevestiging van het aangemaakte account

**Gerelateerde Requirements:** FE1.1, FE1.2, FE1.3, FE1.4, FE1.5

---

### UC1.2: Inloggen

**Actoren:** Student, Docent, Beheerder  
**Precondities:** 
- Gebruiker heeft een geldig account
- Gebruiker is niet ingelogd

**Beschrijving:**  
Een gebruiker logt in op het systeem met e-mailadres en wachtwoord.

**Belangrijke stappen:**
1. Gebruiker navigeert naar de inlogpagina
2. Gebruiker vult e-mailadres in
3. Gebruiker vult wachtwoord in
4. Gebruiker klikt op "Inloggen"
5. Systeem valideert de inloggegevens
6. Systeem controleert of account bestaat en wachtwoord klopt
7. Systeem logt gebruiker in
8. Systeem toont dashboard/homepage voor de gebruiker

**Alternatieve flows:**

**A1: Ongeldige inloggegevens**
- 5a. Systeem detecteert dat e-mailadres of wachtwoord ongeldig is
- 5b. Systeem toont foutmelding: "Ongeldig e-mailadres of wachtwoord"
- 5c. Gebruiker kan opnieuw proberen
- Flow gaat terug naar stap 2

**A2: Account bestaat niet**
- 6a. Systeem detecteert dat account niet bestaat
- 6b. Systeem toont foutmelding: "Ongeldig e-mailadres of wachtwoord"
- 6c. Gebruiker kan opnieuw proberen
- Flow gaat terug naar stap 2

**Postcondities:**
- Gebruiker is ingelogd
- Gebruiker heeft toegang tot functionaliteit op basis van zijn/haar rol
- Gebruiker wordt doorgestuurd naar het dashboard/homepage

**Gerelateerde Requirements:** FE2.1, FE2.2

---

### UC1.3: Wachtwoord vergeten

**Actoren:** Student, Docent, Beheerder  
**Precondities:** 
- Gebruiker heeft een geldig account
- Gebruiker is niet ingelogd

**Beschrijving:**  
Een gebruiker vraagt een wachtwoord reset aan omdat hij/zij het wachtwoord is vergeten.

**Belangrijke stappen:**
1. Gebruiker navigeert naar de inlogpagina
2. Gebruiker klikt op "Wachtwoord vergeten"
3. Systeem toont formulier voor wachtwoord reset
4. Gebruiker vult e-mailadres in
5. Gebruiker klikt op "Reset link versturen"
6. Systeem controleert of e-mailadres bestaat
7. Systeem genereert wachtwoord reset token
8. Systeem stuurt e-mail met reset link naar gebruiker
9. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: E-mailadres bestaat niet**
- 6a. Systeem detecteert dat e-mailadres niet bestaat
- 6b. Systeem toont bevestigingsmelding (om veiligheidsredenen geen specifieke foutmelding)
- Flow eindigt

**Postcondities:**
- Wachtwoord reset e-mail is verstuurd (indien account bestaat)
- Gebruiker kan via de link in de e-mail een nieuw wachtwoord instellen

**Gerelateerde Requirements:** FE2.3

---

### UC1.4: Uitloggen

**Actoren:** Student, Docent, Beheerder  
**Precondities:** 
- Gebruiker is ingelogd

**Beschrijving:**  
Een ingelogde gebruiker logt uit van het systeem.

**Belangrijke stappen:**
1. Gebruiker klikt op "Uitloggen" in het navigatiemenu
2. Systeem bevestigt uitlogactie
3. Systeem logt gebruiker uit
4. Systeem verwijdert sessiegegevens
5. Systeem stuurt gebruiker door naar homepage

**Alternatieve flows:** Geen

**Postcondities:**
- Gebruiker is uitgelogd
- Sessiegegevens zijn verwijderd
- Gebruiker heeft geen toegang meer tot beveiligde functionaliteit
- Gebruiker bevindt zich op de homepage

**Gerelateerde Requirements:** FE3.1, FE3.2

---

## 4. Use Cases Projectbeheer

### UC2.1: Project aanmaken

**Actoren:** Student  
**Precondities:** 
- Student is ingelogd
- Student heeft een geldig account

**Beschrijving:**  
Een student maakt een nieuw project aan met alle benodigde informatie.

**Belangrijke stappen:**
1. Student navigeert naar "Mijn Projecten"
2. Student klikt op "Nieuw project aanmaken"
3. Systeem toont project aanmaakformulier
4. Student vult verplichte velden in:
   - Projecttitel
   - Beschrijving
   - Categorie
   - Technologieën
5. Student vult optionele velden in:
   - Projectlink (verplicht volgens FE5.4)
   - GitHub repository links (optioneel)
6. Student voegt afbeeldingen toe (minimaal 1, maximaal 10)
7. Student koppelt eventueel andere studenten aan het project
8. Student klikt op "Opslaan als concept"
9. Systeem valideert de invoer
10. Systeem slaat project op als "concept"
11. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Verplichte velden ontbreken**
- 9a. Systeem detecteert dat verplichte velden ontbreken
- 9b. Systeem toont foutmelding met ontbrekende velden
- 9c. Student kan ontbrekende velden invullen
- Flow gaat terug naar stap 4

**A2: Te weinig afbeeldingen**
- 9a. Systeem detecteert dat er geen afbeeldingen zijn toegevoegd
- 9b. Systeem toont foutmelding: "Voeg minimaal 1 afbeelding toe"
- 9c. Student kan afbeeldingen toevoegen
- Flow gaat terug naar stap 6

**A3: Te veel afbeeldingen**
- 9a. Systeem detecteert dat er meer dan 10 afbeeldingen zijn toegevoegd
- 9b. Systeem toont foutmelding: "Maximum 10 afbeeldingen toegestaan"
- 9c. Student kan afbeeldingen verwijderen
- Flow gaat terug naar stap 6

**Postcondities:**
- Nieuw project is aangemaakt en opgeslagen als "concept"
- Project is niet zichtbaar voor andere gebruikers
- Student kan het project later bewerken of publiceren

**Gerelateerde Requirements:** FE5.1, FE5.2, FE5.3, FE5.4, FE5.5, FE5.6, FE5.7

---

### UC2.2: Project bewerken

**Actoren:** Student  
**Precondities:** 
- Student is ingelogd
- Student heeft een project aangemaakt
- Project bestaat in het systeem

**Beschrijving:**  
Een student bewerkt een bestaand project van zichzelf.

**Belangrijke stappen:**
1. Student navigeert naar "Mijn Projecten"
2. Student selecteert het project dat hij/zij wil bewerken
3. Student klikt op "Bewerken"
4. Systeem toont project bewerkformulier met huidige gegevens
5. Student wijzigt de gewenste velden
6. Student klikt op "Opslaan"
7. Systeem valideert de wijzigingen
8. Systeem slaat de wijzigingen op
9. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Validatiefouten**
- 7a. Systeem detecteert validatiefouten
- 7b. Systeem toont foutmeldingen
- 7c. Student kan fouten corrigeren
- Flow gaat terug naar stap 5

**A2: Student probeert project van andere student te bewerken**
- 2a. Systeem detecteert dat project niet van deze student is
- 2b. Systeem toont foutmelding: "Je hebt geen rechten om dit project te bewerken"
- Flow eindigt

**Postcondities:**
- Project is bijgewerkt met nieuwe gegevens
- Wijzigingen zijn opgeslagen
- Als project gepubliceerd was, blijven wijzigingen zichtbaar voor bezoekers

**Gerelateerde Requirements:** FE6.1, FE6.2, FE6.3, FE4.3

---

### UC2.3: Project verwijderen

**Actoren:** Student, Beheerder  
**Precondities:** 
- Student is ingelogd OF Beheerder is ingelogd
- Project bestaat in het systeem

**Beschrijving:**  
Een student verwijdert een eigen project, of een beheerder verwijdert een willekeurig project.

**Belangrijke stappen:**
1. Student/Beheerder navigeert naar het project
2. Student/Beheerder klikt op "Verwijderen"
3. Systeem toont bevestigingsdialoog
4. Student/Beheerder bevestigt verwijdering
5. Systeem controleert rechten:
   - Student: alleen eigen projecten
   - Beheerder: alle projecten
6. Systeem verwijdert project uit database
7. Systeem verwijdert gekoppelde afbeeldingen
8. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Gebruiker annuleert verwijdering**
- 4a. Gebruiker klikt op "Annuleren"
- 4b. Systeem sluit bevestigingsdialoog
- Flow eindigt

**A2: Student probeert project van andere student te verwijderen**
- 5a. Systeem detecteert dat student geen rechten heeft
- 5b. Systeem toont foutmelding: "Je hebt geen rechten om dit project te verwijderen"
- Flow eindigt

**Postcondities:**
- Project is verwijderd uit het systeem
- Gekoppelde afbeeldingen zijn verwijderd
- Project is niet meer zichtbaar voor gebruikers

**Gerelateerde Requirements:** FE7.1, FE7.2, FE7.3, FE4.3

---

### UC2.4: Project publiceren

**Actoren:** Student  
**Precondities:** 
- Student is ingelogd
- Student heeft een project aangemaakt als "concept"

**Beschrijving:**  
Een student publiceert een concept project zodat het zichtbaar wordt voor alle bezoekers.

**Belangrijke stappen:**
1. Student navigeert naar "Mijn Projecten"
2. Student selecteert een concept project
3. Student klikt op "Publiceren"
4. Systeem controleert of project alle verplichte velden heeft
5. Systeem wijzigt projectstatus naar "gepubliceerd"
6. Systeem maakt project zichtbaar voor alle bezoekers
7. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Project heeft niet alle verplichte velden**
- 4a. Systeem detecteert ontbrekende velden
- 4b. Systeem toont foutmelding met ontbrekende velden
- 4c. Student moet eerst project bewerken
- Flow eindigt

**A2: Goedkeuring vereist (optioneel)**
- 5a. Als goedkeuring vereist is, wijzigt systeem status naar "wachtend op goedkeuring"
- 5b. Project is nog niet zichtbaar voor bezoekers
- 5c. Docent moet project goedkeuren
- Flow eindigt

**Postcondities:**
- Projectstatus is gewijzigd naar "gepubliceerd" (of "wachtend op goedkeuring")
- Project is zichtbaar voor bezoekers (indien direct gepubliceerd)
- Project verschijnt in projectoverzicht

**Gerelateerde Requirements:** FE8.1, FE8.2, FE8.3

---

### UC2.5: Project goedkeuren

**Actoren:** Docent, Beheerder  
**Precondities:** 
- Docent/Beheerder is ingelogd
- Er zijn projecten die wachten op goedkeuring (indien goedkeuring vereist is)

**Beschrijving:**  
Een docent of beheerder keurt een project goed zodat het publiek zichtbaar wordt.

**Belangrijke stappen:**
1. Docent/Beheerder navigeert naar "Projecten ter goedkeuring"
2. Docent/Beheerder bekijkt een project dat wacht op goedkeuring
3. Docent/Beheerder beoordeelt het project
4. Docent/Beheerder klikt op "Goedkeuren"
5. Systeem wijzigt projectstatus naar "gepubliceerd"
6. Systeem maakt project zichtbaar voor alle bezoekers
7. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Project afwijzen**
- 4a. Docent/Beheerder klikt op "Afwijzen"
- 4b. Systeem vraagt om reden voor afwijzing
- 4c. Docent/Beheerder vult reden in
- 4d. Systeem wijzigt projectstatus naar "afgewezen"
- 4e. Systeem stuurt notificatie naar student
- Flow eindigt

**Postcondities:**
- Projectstatus is gewijzigd naar "gepubliceerd"
- Project is zichtbaar voor alle bezoekers
- Student heeft notificatie ontvangen (indien afgewezen)

**Gerelateerde Requirements:** FE8.3, FE4.4

---

## 5. Use Cases Profielbeheer

### UC3.1: Profiel aanmaken

**Actoren:** Student  
**Precondities:** 
- Student is ingelogd
- Student heeft een account ontvangen van beheerder
- Student heeft nog geen profiel aangemaakt

**Beschrijving:**  
Een student maakt een profiel aan met persoonlijke informatie.

**Belangrijke stappen:**
1. Student navigeert naar "Mijn Profiel"
2. Student klikt op "Profiel aanmaken"
3. Systeem toont profiel aanmaakformulier
4. Student vult profielgegevens in:
   - Voornaam
   - Achternaam
   - Profielfoto (upload)
   - Bio
   - Vaardigheden
   - Contactgegevens
5. Student voegt optioneel links toe naar:
   - LinkedIn
   - GitHub
   - IT Showcase profiel
6. Student klikt op "Profiel opslaan"
7. Systeem valideert de invoer
8. Systeem slaat profiel op
9. Systeem maakt publieke profielpagina aan
10. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Verplichte velden ontbreken**
- 7a. Systeem detecteert ontbrekende verplichte velden
- 7b. Systeem toont foutmelding
- 7c. Student kan ontbrekende velden invullen
- Flow gaat terug naar stap 4

**Postcondities:**
- Profiel is aangemaakt
- Publieke profielpagina is beschikbaar
- Profiel is zichtbaar voor bezoekers

**Gerelateerde Requirements:** FE9.1, FE9.2, FE9.3

---

### UC3.2: Profiel bewerken

**Actoren:** Student  
**Precondities:** 
- Student is ingelogd
- Student heeft een profiel aangemaakt

**Beschrijving:**  
Een student bewerkt zijn/haar bestaande profiel.

**Belangrijke stappen:**
1. Student navigeert naar "Mijn Profiel"
2. Student klikt op "Bewerken"
3. Systeem toont profiel bewerkformulier met huidige gegevens
4. Student wijzigt de gewenste velden
5. Student klikt op "Opslaan"
6. Systeem valideert de wijzigingen
7. Systeem slaat wijzigingen op
8. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Validatiefouten**
- 6a. Systeem detecteert validatiefouten
- 6b. Systeem toont foutmeldingen
- 6c. Student kan fouten corrigeren
- Flow gaat terug naar stap 4

**Postcondities:**
- Profiel is bijgewerkt
- Wijzigingen zijn direct zichtbaar op publieke profielpagina
- Alle gekoppelde projecten tonen bijgewerkte profielinformatie

**Gerelateerde Requirements:** FE10.1, FE10.2, FE10.3

---

### UC3.3: Profiel bekijken

**Actoren:** Bezoeker, Student, Docent, Beheerder  
**Precondities:** 
- Geen (profiel is publiek toegankelijk)

**Beschrijving:**  
Een gebruiker bekijkt het publieke profiel van een student.

**Belangrijke stappen:**
1. Gebruiker navigeert naar studentoverzicht of klikt op link naar studentprofiel
2. Systeem laadt profielpagina
3. Systeem toont profielinformatie:
   - Profielfoto
   - Naam
   - Bio
   - Vaardigheden
   - Contactgegevens
   - Social media links
4. Systeem toont alle gepubliceerde projecten van de student
5. Gebruiker kan op projecten klikken voor meer details

**Alternatieve flows:**

**A1: Profiel bestaat niet**
- 2a. Systeem detecteert dat profiel niet bestaat
- 2b. Systeem toont foutmelding: "Profiel niet gevonden"
- Flow eindigt

**Postcondities:**
- Gebruiker heeft profielinformatie bekeken
- Gebruiker kan doorklikken naar projecten

**Gerelateerde Requirements:** FE11.1, FE11.2, FE11.3

---

## 6. Use Cases Contentweergave

### UC4.1: Projectoverzicht bekijken

**Actoren:** Bezoeker, Student, Docent, Beheerder  
**Precondities:** 
- Geen (overzicht is publiek toegankelijk)

**Beschrijving:**  
Een gebruiker bekijkt een overzicht van alle gepubliceerde projecten.

**Belangrijke stappen:**
1. Gebruiker navigeert naar projectoverzicht (homepage of projecten pagina)
2. Systeem laadt gepubliceerde projecten
3. Systeem toont projecten als kaarten met:
   - Afbeelding
   - Titel
   - Korte beschrijving
   - Categorie
   - Technologieën
4. Systeem toont paginering (bijvoorbeeld 12 projecten per pagina)
5. Gebruiker kan naar volgende/vorige pagina navigeren
6. Gebruiker kan op een project klikken voor details

**Alternatieve flows:**

**A1: Geen projecten beschikbaar**
- 2a. Systeem detecteert dat er geen gepubliceerde projecten zijn
- 2b. Systeem toont melding: "Er zijn nog geen projecten beschikbaar"
- Flow eindigt

**A2: Sorteren op datum of populariteit**
- 3a. Gebruiker selecteert sorteeroptie (nieuwste eerst, populariteit)
- 3b. Systeem sorteert projecten volgens selectie
- 3c. Systeem toont gesorteerde projecten
- Flow gaat terug naar stap 3

**Postcondities:**
- Gebruiker heeft projectoverzicht bekeken
- Gebruiker kan doorklikken naar projectdetails

**Gerelateerde Requirements:** FE12.1, FE12.2, FE12.3, FE12.4

---

### UC4.2: Projectdetails bekijken

**Actoren:** Bezoeker, Student, Docent, Beheerder  
**Precondities:** 
- Project bestaat en is gepubliceerd (of gebruiker is eigenaar/docent/beheerder)

**Beschrijving:**  
Een gebruiker bekijkt de details van een specifiek project.

**Belangrijke stappen:**
1. Gebruiker klikt op een project in het overzicht
2. Systeem laadt projectdetailpagina
3. Systeem toont volledige projectinformatie:
   - Titel
   - Volledige beschrijving
   - Alle afbeeldingen
   - Categorie
   - Technologieën
   - Betrokken studenten (met links naar profielen)
   - Projectlink
   - GitHub repository links (indien aanwezig)
4. Gebruiker kan doorklikken naar studentprofielen
5. Gebruiker kan doorklikken naar externe links

**Alternatieve flows:**

**A1: Project bestaat niet**
- 2a. Systeem detecteert dat project niet bestaat
- 2b. Systeem toont foutmelding: "Project niet gevonden"
- Flow eindigt

**A2: Project is niet gepubliceerd**
- 2a. Systeem detecteert dat project nog niet gepubliceerd is
- 2b. Als gebruiker niet de eigenaar/docent/beheerder is, toont systeem foutmelding
- 2c. Flow eindigt

**Postcondities:**
- Gebruiker heeft projectdetails bekeken
- Gebruiker kan doorklikken naar gerelateerde informatie

**Gerelateerde Requirements:** FE13.1, FE13.2, FE13.3

---

### UC4.3: Studentoverzicht bekijken

**Actoren:** Bezoeker, Student, Docent, Beheerder  
**Precondities:** 
- Geen (overzicht is publiek toegankelijk)

**Beschrijving:**  
Een gebruiker bekijkt een overzicht van alle studenten met profielen.

**Belangrijke stappen:**
1. Gebruiker navigeert naar studentoverzicht
2. Systeem laadt alle studenten met profielen
3. Systeem toont studenten als kaarten met:
   - Profielfoto
   - Naam
   - Korte bio
4. Systeem toont paginering
5. Gebruiker kan naar volgende/vorige pagina navigeren
6. Gebruiker kan op een student klikken voor profieldetails

**Alternatieve flows:**

**A1: Geen studenten beschikbaar**
- 2a. Systeem detecteert dat er geen studenten met profielen zijn
- 2b. Systeem toont melding: "Er zijn nog geen studentprofielen beschikbaar"
- Flow eindigt

**Postcondities:**
- Gebruiker heeft studentoverzicht bekeken
- Gebruiker kan doorklikken naar studentprofielen

**Gerelateerde Requirements:** FE14.1, FE14.2, FE14.3

---

### UC4.4: Dashboard Showcase bekijken

**Actoren:** Bezoeker, Student, Docent, Beheerder  
**Precondities:** 
- Geen (showcase is publiek toegankelijk)

**Beschrijving:**  
Een gebruiker bekijkt de dashboard showcase met de beste projecten.

**Belangrijke stappen:**
1. Gebruiker navigeert naar homepage/dashboard
2. Systeem laadt showcase projecten
3. Systeem toont maximaal 12 projecten prominent op het dashboard
4. Gebruiker kan projecten bekijken
5. Gebruiker kan doorklikken naar projectdetails

**Alternatieve flows:**

**A1: Geen showcase projecten**
- 2a. Systeem detecteert dat er geen showcase projecten zijn
- 2b. Systeem toont standaard projectoverzicht
- Flow gaat verder met UC4.1

**Postcondities:**
- Gebruiker heeft showcase projecten bekeken
- Gebruiker kan doorklikken naar projectdetails

**Gerelateerde Requirements:** FE14A.1, FE14A.2, FE14A.3, FE14A.8

---

### UC4.5: Project toevoegen aan Showcase

**Actoren:** Docent, Beheerder  
**Precondities:** 
- Docent/Beheerder is ingelogd
- Er zijn gepubliceerde projecten beschikbaar
- Showcase heeft nog geen 12 projecten (indien limiet actief)

**Beschrijving:**  
Een docent of beheerder voegt een project toe aan de dashboard showcase.

**Belangrijke stappen:**
1. Docent/Beheerder navigeert naar showcase beheer
2. Docent/Beheerder bekijkt lijst van gepubliceerde projecten
3. Docent/Beheerder selecteert een project
4. Docent/Beheerder klikt op "Toevoegen aan showcase"
5. Systeem controleert of project gepubliceerd is
6. Systeem controleert of showcase nog ruimte heeft (maximaal 12)
7. Systeem voegt project toe aan showcase
8. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Project is niet gepubliceerd**
- 5a. Systeem detecteert dat project niet gepubliceerd is
- 5b. Systeem toont foutmelding: "Alleen gepubliceerde projecten kunnen aan showcase worden toegevoegd"
- Flow eindigt

**A2: Showcase is vol**
- 6a. Systeem detecteert dat showcase al 12 projecten bevat
- 6b. Systeem toont foutmelding: "Showcase is vol. Verwijder eerst een project."
- Flow eindigt

**Postcondities:**
- Project is toegevoegd aan showcase
- Project wordt prominent getoond op dashboard/homepage
- Alle bezoekers kunnen showcase projecten zien

**Gerelateerde Requirements:** FE14A.4, FE14A.7

---

### UC4.6: Project verwijderen uit Showcase

**Actoren:** Docent, Beheerder  
**Precondities:** 
- Docent/Beheerder is ingelogd
- Er zijn projecten in de showcase

**Beschrijving:**  
Een docent of beheerder verwijdert een project uit de showcase.

**Belangrijke stappen:**
1. Docent/Beheerder navigeert naar showcase beheer
2. Docent/Beheerder bekijkt huidige showcase projecten
3. Docent/Beheerder selecteert een project
4. Docent/Beheerder klikt op "Verwijderen uit showcase"
5. Systeem vraagt om bevestiging
6. Docent/Beheerder bevestigt verwijdering
7. Systeem verwijdert project uit showcase
8. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Gebruiker annuleert verwijdering**
- 6a. Gebruiker klikt op "Annuleren"
- 6b. Systeem sluit bevestigingsdialoog
- Flow eindigt

**Postcondities:**
- Project is verwijderd uit showcase
- Project blijft wel gepubliceerd, maar wordt niet meer prominent getoond
- Showcase toont bijgewerkte lijst

**Gerelateerde Requirements:** FE14A.5

---

### UC4.7: Volgorde showcase projecten aanpassen

**Actoren:** Docent, Beheerder  
**Precondities:** 
- Docent/Beheerder is ingelogd
- Er zijn meerdere projecten in de showcase

**Beschrijving:**  
Een docent of beheerder past de volgorde van projecten in de showcase aan.

**Belangrijke stappen:**
1. Docent/Beheerder navigeert naar showcase beheer
2. Docent/Beheerder bekijkt huidige showcase projecten
3. Docent/Beheerder gebruikt drag-and-drop of pijltjes om volgorde aan te passen
4. Systeem slaat nieuwe volgorde op
5. Systeem toont bevestigingsmelding

**Alternatieve flows:** Geen

**Postcondities:**
- Volgorde van showcase projecten is aangepast
- Nieuwe volgorde wordt getoond op dashboard/homepage

**Gerelateerde Requirements:** FE14A.6

---

## 7. Use Cases Zoeken en Filteren

### UC5.1: Zoeken naar projecten

**Actoren:** Bezoeker, Student, Docent, Beheerder  
**Precondities:** 
- Geen (zoekfunctionaliteit is publiek toegankelijk)

**Beschrijving:**  
Een gebruiker zoekt naar projecten op basis van zoekterm.

**Belangrijke stappen:**
1. Gebruiker navigeert naar homepage of projectoverzicht
2. Gebruiker ziet zoekbalk
3. Gebruiker voert zoekterm in (bijvoorbeeld: "React", "Web Development", studentnaam)
4. Gebruiker klikt op "Zoeken" of drukt op Enter
5. Systeem zoekt in:
   - Projecttitels
   - Projectbeschrijvingen
   - Technologieën
   - Studentnamen
   - Vaardigheden
6. Systeem toont zoekresultaten
7. Gebruiker kan op resultaten klikken voor details

**Alternatieve flows:**

**A1: Geen resultaten gevonden**
- 6a. Systeem vindt geen overeenkomende projecten
- 6b. Systeem toont melding: "Geen resultaten gevonden voor '[zoekterm]'"
- 6c. Gebruiker kan nieuwe zoekopdracht uitvoeren
- Flow gaat terug naar stap 3

**A2: Lege zoekterm**
- 4a. Gebruiker klikt op zoeken zonder term in te voeren
- 4b. Systeem toont alle projecten (of geen actie)
- Flow eindigt

**Postcondities:**
- Gebruiker heeft zoekresultaten bekeken
- Gebruiker kan doorklikken naar gevonden projecten

**Gerelateerde Requirements:** FE15.1, FE15.2, FE15.3, FE15.4

---

### UC5.2: Filteren op categorie

**Actoren:** Bezoeker, Student, Docent, Beheerder  
**Precondities:** 
- Geen (filterfunctionaliteit is publiek toegankelijk)

**Beschrijving:**  
Een gebruiker filtert projecten op basis van categorie.

**Belangrijke stappen:**
1. Gebruiker navigeert naar projectoverzicht
2. Gebruiker ziet filteropties
3. Gebruiker selecteert een categorie (bijvoorbeeld: "Web Development", "Mobile App")
4. Systeem filtert projecten op geselecteerde categorie
5. Systeem toont gefilterde projecten
6. Gebruiker kan filters combineren met andere filters

**Alternatieve flows:**

**A1: Geen projecten in categorie**
- 5a. Systeem vindt geen projecten in geselecteerde categorie
- 5b. Systeem toont melding: "Geen projecten gevonden in deze categorie"
- Flow eindigt

**A2: Filter resetten**
- 3a. Gebruiker klikt op "Filters resetten"
- 3b. Systeem verwijdert alle actieve filters
- 3c. Systeem toont alle projecten
- Flow eindigt

**Postcondities:**
- Gebruiker heeft gefilterde projecten bekeken
- Filters blijven actief totdat ze worden gereset

**Gerelateerde Requirements:** FE16.1, FE16.4, FE16.5

---

### UC5.3: Filteren op technologieën

**Actoren:** Bezoeker, Student, Docent, Beheerder  
**Precondities:** 
- Geen (filterfunctionaliteit is publiek toegankelijk)

**Beschrijving:**  
Een gebruiker filtert projecten op basis van gebruikte technologieën.

**Belangrijke stappen:**
1. Gebruiker navigeert naar projectoverzicht
2. Gebruiker ziet filteropties
3. Gebruiker selecteert een of meerdere technologieën (bijvoorbeeld: "React", "PHP", "MySQL")
4. Systeem filtert projecten op geselecteerde technologieën
5. Systeem toont gefilterde projecten
6. Gebruiker kan filters combineren met andere filters

**Alternatieve flows:**

**A1: Geen projecten met technologie**
- 5a. Systeem vindt geen projecten met geselecteerde technologie
- 5b. Systeem toont melding: "Geen projecten gevonden met deze technologie"
- Flow eindigt

**Postcondities:**
- Gebruiker heeft gefilterde projecten bekeken
- Filters blijven actief

**Gerelateerde Requirements:** FE16.2, FE16.4, FE16.5

---

### UC5.4: Meerdere filters combineren

**Actoren:** Bezoeker, Student, Docent, Beheerder  
**Precondities:** 
- Geen (filterfunctionaliteit is publiek toegankelijk)

**Beschrijving:**  
Een gebruiker combineert meerdere filters om specifieke projecten te vinden.

**Belangrijke stappen:**
1. Gebruiker navigeert naar projectoverzicht
2. Gebruiker selecteert meerdere filters:
   - Categorie
   - Technologieën
   - Opleidingsjaar (indien beschikbaar)
3. Systeem combineert alle actieve filters
4. Systeem toont projecten die aan alle filters voldoen
5. Gebruiker kan filters aanpassen of resetten

**Alternatieve flows:**

**A1: Geen resultaten met gecombineerde filters**
- 4a. Systeem vindt geen projecten die aan alle filters voldoen
- 4b. Systeem toont melding: "Geen projecten gevonden met deze filtercombinatie"
- 4c. Gebruiker kan filters aanpassen
- Flow gaat terug naar stap 2

**Postcondities:**
- Gebruiker heeft gefilterde projecten bekeken
- Meerdere filters zijn actief

**Gerelateerde Requirements:** FE16.3, FE16.4, FE16.5

---

## 8. Use Cases Beheerfunctionaliteit

### UC6.1: Project modereren

**Actoren:** Beheerder  
**Precondities:** 
- Beheerder is ingelogd
- Er zijn projecten in het systeem

**Beschrijving:**  
Een beheerder bekijkt en modereert projecten.

**Belangrijke stappen:**
1. Beheerder navigeert naar "Content Moderatie"
2. Beheerder bekijkt lijst van projecten
3. Beheerder selecteert een project
4. Beheerder bekijkt projectdetails
5. Beheerder kan:
   - Project goedkeuren
   - Project bewerken
   - Project verwijderen
   - Project verbergen
6. Beheerder voert gekozen actie uit
7. Systeem voert actie uit
8. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Project verbergen**
- 5a. Beheerder klikt op "Verbergen"
- 5b. Systeem verbergt project voor bezoekers
- 5c. Project blijft zichtbaar voor beheerder
- Flow eindigt

**Postcondities:**
- Project is gemodereerd
- Actie is uitgevoerd (goedkeuring/bewerking/verwijdering/verbergen)

**Gerelateerde Requirements:** FE17.1, FE17.2, FE17.3

---

### UC6.2: Gebruikers beheren

**Actoren:** Beheerder  
**Precondities:** 
- Beheerder is ingelogd

**Beschrijving:**  
Een beheerder beheert gebruikersaccounts.

**Belangrijke stappen:**
1. Beheerder navigeert naar "Gebruikersbeheer"
2. Systeem toont lijst van alle gebruikers
3. Beheerder kan per gebruiker:
   - Account bekijken
   - Rol aanpassen
   - Account deactiveren
   - Account verwijderen
   - Wachtwoord resetten
4. Beheerder selecteert gebruiker en actie
5. Systeem voert actie uit
6. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Wachtwoord resetten**
- 4a. Beheerder klikt op "Wachtwoord resetten"
- 4b. Systeem genereert tijdelijk wachtwoord
- 4c. Systeem stuurt nieuw wachtwoord naar gebruiker per e-mail
- 4d. Systeem toont bevestigingsmelding
- Flow eindigt

**A2: Account deactiveren**
- 4a. Beheerder klikt op "Account deactiveren"
- 4b. Systeem vraagt om bevestiging
- 4c. Beheerder bevestigt
- 4d. Systeem deactiveert account
- 4e. Gebruiker kan niet meer inloggen
- Flow eindigt

**Postcondities:**
- Gebruikersaccount is beheerd
- Actie is uitgevoerd
- Gebruiker heeft notificatie ontvangen (indien van toepassing)

**Gerelateerde Requirements:** FE18.1, FE18.2, FE18.3, FE18.4, FE18.5

---

### UC6.3: Categorieën beheren

**Actoren:** Beheerder  
**Precondities:** 
- Beheerder is ingelogd

**Beschrijving:**  
Een beheerder beheert projectcategorieën.

**Belangrijke stappen:**
1. Beheerder navigeert naar "Systeemconfiguratie"
2. Beheerder selecteert "Categorieën beheren"
3. Systeem toont lijst van bestaande categorieën
4. Beheerder kan:
   - Nieuwe categorie toevoegen
   - Bestaande categorie bewerken
   - Categorie verwijderen
5. Beheerder voert gekozen actie uit
6. Systeem valideert invoer
7. Systeem slaat wijzigingen op
8. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Categorie verwijderen die nog gebruikt wordt**
- 5a. Beheerder probeert categorie te verwijderen die nog door projecten wordt gebruikt
- 5b. Systeem detecteert dat categorie nog in gebruik is
- 5c. Systeem toont foutmelding: "Deze categorie wordt nog gebruikt door projecten en kan niet worden verwijderd"
- Flow eindigt

**Postcondities:**
- Categorieën zijn beheerd
- Wijzigingen zijn opgeslagen
- Nieuwe categorieën zijn beschikbaar voor projecten

**Gerelateerde Requirements:** FE19.2

---

### UC6.4: Technologieën beheren

**Actoren:** Beheerder  
**Precondities:** 
- Beheerder is ingelogd

**Beschrijving:**  
Een beheerder beheert technologieën die gebruikt kunnen worden in projecten.

**Belangrijke stappen:**
1. Beheerder navigeert naar "Systeemconfiguratie"
2. Beheerder selecteert "Technologieën beheren"
3. Systeem toont lijst van bestaande technologieën
4. Beheerder kan:
   - Nieuwe technologie toevoegen
   - Bestaande technologie bewerken
   - Technologie verwijderen
5. Beheerder voert gekozen actie uit
6. Systeem valideert invoer
7. Systeem slaat wijzigingen op
8. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Technologie verwijderen die nog gebruikt wordt**
- 5a. Beheerder probeert technologie te verwijderen die nog door projecten wordt gebruikt
- 5b. Systeem detecteert dat technologie nog in gebruik is
- 5c. Systeem toont foutmelding: "Deze technologie wordt nog gebruikt door projecten en kan niet worden verwijderd"
- Flow eindigt

**Postcondities:**
- Technologieën zijn beheerd
- Wijzigingen zijn opgeslagen
- Nieuwe technologieën zijn beschikbaar voor projecten

**Gerelateerde Requirements:** FE19.2

---

### UC6.5: Systeeminstellingen aanpassen

**Actoren:** Beheerder  
**Precondities:** 
- Beheerder is ingelogd

**Beschrijving:**  
Een beheerder past algemene systeeminstellingen aan.

**Belangrijke stappen:**
1. Beheerder navigeert naar "Systeemconfiguratie"
2. Beheerder selecteert "Algemene Instellingen"
3. Systeem toont instellingenpagina
4. Beheerder past instellingen aan (bijvoorbeeld:
   - Project goedkeuring vereist (ja/nee)
   - Maximum aantal showcase projecten
   - Standaard items per pagina)
5. Beheerder klikt op "Opslaan"
6. Systeem valideert instellingen
7. Systeem slaat instellingen op
8. Systeem toont bevestigingsmelding

**Alternatieve flows:**

**A1: Ongeldige instellingen**
- 6a. Systeem detecteert ongeldige instellingen
- 6b. Systeem toont foutmelding
- 6c. Beheerder kan instellingen corrigeren
- Flow gaat terug naar stap 4

**Postcondities:**
- Systeeminstellingen zijn aangepast
- Wijzigingen zijn actief
- Systeem gedraagt zich volgens nieuwe instellingen

**Gerelateerde Requirements:** FE19.1

---

## Bijlagen

### Bijlage A: Use Case Overzicht

| Use Case ID | Naam | Actoren | Prioriteit |
|-------------|------|---------|------------|
| UC1.1 | Gebruikersaccount aanmaken | Beheerder | Must Have |
| UC1.2 | Inloggen | Student, Docent, Beheerder | Must Have |
| UC1.3 | Wachtwoord vergeten | Student, Docent, Beheerder | Should Have |
| UC1.4 | Uitloggen | Student, Docent, Beheerder | Must Have |
| UC2.1 | Project aanmaken | Student | Must Have |
| UC2.2 | Project bewerken | Student | Must Have |
| UC2.3 | Project verwijderen | Student, Beheerder | Must Have |
| UC2.4 | Project publiceren | Student | Must Have |
| UC2.5 | Project goedkeuren | Docent, Beheerder | Should Have |
| UC3.1 | Profiel aanmaken | Student | Must Have |
| UC3.2 | Profiel bewerken | Student | Must Have |
| UC3.3 | Profiel bekijken | Alle | Must Have |
| UC4.1 | Projectoverzicht bekijken | Alle | Must Have |
| UC4.2 | Projectdetails bekijken | Alle | Must Have |
| UC4.3 | Studentoverzicht bekijken | Alle | Must Have |
| UC4.4 | Dashboard Showcase bekijken | Alle | Should Have |
| UC4.5 | Project toevoegen aan Showcase | Docent, Beheerder | Should Have |
| UC4.6 | Project verwijderen uit Showcase | Docent, Beheerder | Should Have |
| UC4.7 | Volgorde showcase projecten aanpassen | Docent, Beheerder | Should Have |
| UC5.1 | Zoeken naar projecten | Alle | Must Have |
| UC5.2 | Filteren op categorie | Alle | Must Have |
| UC5.3 | Filteren op technologieën | Alle | Must Have |
| UC5.4 | Meerdere filters combineren | Alle | Should Have |
| UC6.1 | Project modereren | Beheerder | Should Have |
| UC6.2 | Gebruikers beheren | Beheerder | Should Have |
| UC6.3 | Categorieën beheren | Beheerder | Should Have |
| UC6.4 | Technologieën beheren | Beheerder | Should Have |
| UC6.5 | Systeeminstellingen aanpassen | Beheerder | Should Have |

---

**Document Status:** Gepubliceerd  
**Volgende Stap:** Document is goedgekeurd en vrijgegeven voor gebruik

---

**Laatste Update:** 2026-01-11
