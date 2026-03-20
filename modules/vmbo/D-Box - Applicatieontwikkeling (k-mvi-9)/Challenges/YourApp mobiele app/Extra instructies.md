# Extra instructies en leersteun

Dit bestand hoort bij `Challenge.md` in dezelfde map.

## Korte samenvatting

Leerlingen maken een mobiele versie van YourApp. Ze gebruiken hun bestaande HTML/CSS en passen vooral layout en navigatie aan zodat alles leesbaar en klikbaar is op smalle schermen. Daarna testen ze minimaal 3 schermen en leveren ze screenshots en testnotities in.


## Waar uitleg nodig is

1. **Probleem:** Leerlingen snappen niet wat “smalle weergave” betekent in de browser.  
   **Mini-uitleg / leerdoel:** Ze kunnen uitleggen dat je in de browservensterbreedte test (mobiele weergave).
2. **Probleem:** Media queries worden niet toegepast of werken niet zoals verwacht.  
   **Mini-uitleg / leerdoel:** Ze gebruiken één duidelijke breakpoint (bijv. `max-width`).
3. **Probleem:** Knoppen zijn te klein of liggen te dicht bij elkaar.  
   **Mini-uitleg / leerdoel:** Ze vergroten touch-areas en gebruiken spacing (padding/margin).
4. **Probleem:** Formulieren overlappen op mobiel.  
   **Mini-uitleg / leerdoel:** Ze zetten velden onder elkaar met flex/grid op smalle breedte.
5. **Probleem:** Navigatie werkt niet meer na aanpassingen.  
   **Mini-uitleg / leerdoel:** Ze checken links en (als er JS is) menu openen/sluiten.


## Instructies (voor docent of leerling)

### 1) Testen op mobiel: eerst alleen layout, dan pas interactie

1. Open je website in de browser.
2. Verklein het scherm tot ongeveer telefoon-breedte (bijv. 360 tot 430 px).
3. Controleer: tekst blijft leesbaar, knoppen zijn klikbaar, en er is geen overlap.

**Check:** Je ziet minstens 1 scherm duidelijk verbeterd in smalle weergave.


### 2) Media query gebruiken om elementen onder elkaar te zetten

1. Maak in je CSS één media query, bijvoorbeeld: `@media (max-width: 600px) { ... }`.
2. Gebruik binnen die query simpele regels: kaarten stapelen, menu anders tonen, of vaste breedtes aanpassen.
3. Test opnieuw en pas aan tot het rustig is.

**Check:** Op smal past alles zonder grote afsnijding.


### 3) Knoppen en invulvelden mobiel-proof maken

1. Geef knoppen minimaal voldoende padding zodat je niet “naast” klikt.
2. Zorg dat labels bij velden horen en dat velden niet over elkaar schuiven.

**Check:** Je kunt een formulier invullen op smal zonder dat je velden kwijt bent.

