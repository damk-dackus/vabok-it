# Testing Agile Projects
## Presentatie over Agile Testing Methodologieën

*Gebaseerd op de cursus door Ash Coleman*

---

## Slide 1: Introductie

### Testing Agile Projects

**Kernboodschap:**
- Testing heeft de grootste impact wanneer het parallel met projectwerk gebeurt
- ❌ **NIET:** Build software first, test it last
- ✅ **WEL:** Testen van kickoff tot delivery
- Validatie en verificatie op elke ontwikkelstap

**Doel:** Robuuste testprocessen bouwen die Agile methodologieën aanvullen

---

## Slide 2: Wat is Agile Testing?

### Testing in de Agile Context

**Traditioneel denken:**
- Testen aan het einde van het ontwikkelproces
- "Build software first, test it last"

**Agile Testing:**
- Interactief, zelforganiserend proces
- Ervaring en samenwerking bepalen effectiviteit
- Integratie op beste punten in workflow
- Maximale feedback mogelijkheden
- Kwaliteitscontroles in elke beslissingsfase

**Resultaat:** Product van hoogste kwaliteit met correctheid en volledigheid

---

## Slide 3: Shifting Left

### Het Concept van Vroeg Testen

**Het probleem:**
- "Ik had dit eerder moeten weten"
- "Waarom vertel je me dit nu pas?"
- Testers krijgen code in laatste fase
- Weinig tijd voor meer dan oppervlakkige goedkeuring

**De oplossing: Shifting Left**
- Vroege integraties voor snellere feedback
- Regelmatige testintegraties onderweg
- Meer transparantie tijdens ontwikkeling

**Testmogelijkheden binnen een sprint:**
1. Feature ideation → Validatie
2. Ticket creation met acceptance criteria → Validatie
3. Engineering ideation → Verificatie
4. Design, copy, legal → Verificatie
5. Code complete → Testen en verificatie

---

## Slide 4: Test Collaborations

### Samenwerking Centraal

**Agile Manifesto:**
> "We value individuals and interactions over tools and process"

**Rol van Agile Tester:**
- Valideert iteraties van project
- Genereert real-time data over productkwaliteit
- Creëert constructieve feedback
- Snapshot van productstatus voor team

**Belangrijke relaties:**
- Design team
- Development team
- Product team
- Copy team
- Legal team

**Resultaat:** Korte feedback loops → Snellere positieve veranderingen

---

## Slide 5: Backlog Grooming

### Testers in Planning Meetings

**Wat is Backlog Grooming?**
- Meeting om user stories/tickets te bespreken
- Verfijnen voordat ze in sprint worden opgenomen

**Waarom testers betrekken?**
- Dependencies identificeren
- Testbaarheid bepalen
- Tijd voor testen inschatten
- Tekortkomingen in scope blootleggen

**Voordeel:**
- Testen integreren in beginfase project
- Kwaliteit vroeg overwegen
- **Zelfs voordat ontwikkeling begint!**

---

## Slide 6: The Three Amigos

### De Kracht van Drie

**Het concept:**
- Stakeholder
- Developer
- Tester

**Waarom drie?**
- Drie verschillende perspectieven
- Drie verschillende vragen:
  - Developer: "Is dit nog steeds wat ik bouw?"
  - Stakeholder: "Is de story nog steeds deze grootte?"
  - Tester: "Voldoen deze acceptance criteria?"

**Resultaat:**
- Alle mogelijkheden voor uitvoering overwegen
- Elke aspect van story uitdagen
- Duidelijk begrip voordat bouwen begint

---

## Slide 7: Story Kickoff

### Herijken van Verwachtingen

**Het probleem:**
- Technologie evolueert constant
- Van planning tot development komt nieuwe informatie beschikbaar
- Scope kan tegenstrijdig zijn met planning

**Waarom Story Kickoff?**
- Technologie/deliverables kunnen veranderd zijn
- Duidelijke verwachtingen vaststellen
- Met Three Amigos bespreken

**Wat bespreken:**
- Finaliseren acceptance criteria
- Wijzigingen in ontwikkelplan
- Testaanpak
- Alle informatie die uitvoering duidelijk maakt

---

## Slide 8: Testing Estimations

### De Rol van Tester Verandert

**Drie fasen, drie rollen:**

**1. Forager (Backlog Grooming)**
- Algemene testaanpak op hoog niveau
- Vragen over clients, platforms, devices
- Losse testplan

**2. Investigator (Sprint Planning)**
- Gedetailleerde vragen
- Testplan met methoden
- Tools, plugins, data nodig voor testen
- Bevestigen alle task criteria

**3. Flagman (Story Kickoff)**
- Finale checks
- Test execution matrix
- Coverage approach, quality execution, automation

**Kern:** Tester moet informatie discovery bezitten!

---

## Slide 9: Workflow

### Orde van Operaties

**Projectstructuur:**
- **Epics:** Componenten die samen het hele product vormen
- **Stories:** Acties om functionaliteit te bouwen
- **Tasks:** Werk los van ontwikkeling (bijv. copy)

**Belangrijke definities:**
- **Definition of Ready:** Wat nodig is om te beginnen
- **Definition of Done:** Wat nodig is om compleet te zijn

**Waarom belangrijk?**
- Duidelijke verwachtingen voor team
- Beslissingen wanneer tasks nodig zijn
- Wanneer stories klaar zijn voor handoff
- Testers kunnen alle componenten testen wanneer compleet

---

## Slide 10: Test Plan

### Wat, Waar en Op Welke Devices?

**Drie kernvragen:**
1. **Wat te testen?**
   - Wat bouwen we?
   - Waarom bouwen we dit?
   - Voor wie bouwen we dit?

2. **Waar te testen?**
   - Browsers (Google Analytics, Looker, Fabric)
   - Gebruikspatronen analyseren

3. **Op welke devices?**
   - Schermgroottes en breakpoints
   - Operating systems

**Test Plan:**
- Algemene gids voor scope van werk
- Geschreven of mind mapped
- Volgt alle productcomponenten
- Bepaalt aanpak voor kwaliteit

---

## Slide 11: Test Matrices

### Efficiënt Testen

**Het doel:**
- Efficiëntie, niet snelheid
- Belangrijkste platforms identificeren
- Redundante tests voorkomen

**Voorbeeld:**
- Safari op iPhone OF iPad (niet beide)
- Zelfde OS = redundante test
- Test matrix documenteert optimale combinaties

**Voordelen:**
- Minder testtijd
- Focus op hoogste gebruik
- Realistische testplan

---

## Slide 12: Test Automation

### Wanneer Automatiseren?

**Waarom automatiseren?**
- Tests die te snel/massaal zijn voor mensen
- Load testing
- Extreme condities
- Regression suites

**Wanneer automatiseren?**
- ✅ Tests die frequent moeten draaien
- ✅ Tests die te complex zijn voor handmatig
- ✅ Redundante tests
- ❌ Test die 1x per 6 maanden draait (10 stappen) = niet waard

**Voorbeeld:**
- Test elke 5 minuten met 10 stappen = automatiseren!
- Automatisering ondersteunt handmatige testen
- Identificeert onverwachte wijzigingen

---

## Slide 13: Action Outcomes

### Feedback Loops en Projectstatus

**Agile Ceremonies:**
- Regelmatige communicatie binnen team
- Feedback loops identificeren risico's
- Course correction mogelijkheden
- Kwaliteitsbeoordeling

**Rol van Tester:**
- Vergelijken product met acceptance criteria
- Risico's beoordelen en mitigeren
- Projectstatus tegen verwachtingen
- Product health details verschaffen

**Resultaat:**
- Team begrijpt hoe sterk product is
- Samen proces verfijnen
- Kwaliteitsproduct creëren

---

## Slide 14: Key Takeaways

### Belangrijkste Leerpunten

1. **Testen vanaf het begin**
   - Niet wachten tot het einde
   - Integratie in elke fase

2. **Samenwerking is cruciaal**
   - Three Amigos concept
   - Korte feedback loops

3. **Planning en voorbereiding**
   - Backlog grooming
   - Story kickoff
   - Test plan

4. **Efficiëntie**
   - Test matrices
   - Automatisering waar nodig
   - Focus op belangrijkste platforms

5. **Continue feedback**
   - Regelmatige communicatie
   - Action outcomes
   - Product health monitoring

---

## Slide 15: Afsluiting

### Agile Testing is als Koekjes Bakken

> "By verifying and validating your work along the way, you can make small adjustments that will delight your users in the end."

**Kernboodschap:**
- Testen is een continu proces
- Kleine aanpassingen onderweg
- Eindresultaat: Blije gebruikers

**Volgende stappen:**
- Implementeer Shifting Left in je team
- Betrek testers in planning meetings
- Creëer korte feedback loops
- Blijf leren en verbeteren

---

## Slide 16: Vragen?

### Bedankt voor je aandacht!

**Contact & Verder Leren:**
- Cursus: "Testing Agile Projects" door Ash Coleman
- Blijf leren over Agile Testing
- Implementeer deze concepten in je eigen team

**Bronnen:**
- Transcriptie cursus Agile Testing
- Belangrijkste Begrippen Agile Testing document

---

*Presentatie samengesteld op basis van de cursus "Testing Agile Projects" door Ash Coleman*
