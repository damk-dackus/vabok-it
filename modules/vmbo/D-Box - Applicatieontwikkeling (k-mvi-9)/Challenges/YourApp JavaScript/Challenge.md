Challenge 10 – Website JavaScript (YourApp)
============================================

Je voegt **interactie** toe aan YourApp met **JavaScript**. Je gebruikt je HTML en CSS van de vorige challenges zodat de opbouw al klopt. Met JavaScript maak je kleine acties die je ziet en kunt testen, zoals het openen van een menu of het tonen van een bericht bij een formulier. Reken op **6 uur** voor het toevoegen van de JavaScript-functies.

Je gebruikt geen frameworks zoals React. Je schrijft plain JavaScript.


## Eindproduct

Je levert in waar je docent het vraagt.

In dit eindproduct:

- **JavaScript-code:** minimaal 1 bestand, bijvoorbeeld `script.js` (of een `<script>` blok als je docent dat toestaat).
- **Minstens 2 werkende interacties:** kies 2 uit deze voorbeelden:
  - menu openen/sluiten (bij mobiel of small scherm) met een knop;
  - een “inbox” of “succes”-bericht na het versturen van een formulier;
  - een eenvoudige knop die een tekstblok laat zien of verbergen;
  - een modal/popup met een knop om te sluiten (mag simpel).
- **Bewijs:** screenshots van beide interacties of een korte uitleg + screenshot.
- **Korte toelichting (max. 6 zinnen):** welke interacties je maakte en waar in je code je dat toevoegde.

De docent gebruikt dit om te zien of je JavaScript de pagina echt laat reageren.


## Deel 1 – Interacties kiezen en plannen

1. Kies 2 interacties uit de lijst (minstens 1 bij voorkeur voor mobiel of navigatie).
2. Schrijf per interactie in 1 zin: wat doet de gebruiker en wat verandert er op het scherm.
3. Maak een mini-schema: knop/veld -> gebeurtenis -> effect (bijvoorbeeld toon/verberg).
4. Geef aan waar je de code ongeveer plaatst (welke pagina of algemeen voor alle pagina's).


## Deel 2 – JavaScript bouwen

1. Zorg dat je JavaScript wordt ingeladen op je pagina, bijvoorbeeld met `<script src="script.js"></script>`.
2. Gebruik `document.querySelector` of `getElementById` om elementen te vinden.
3. Voeg per interactie een event toe met `addEventListener` (bij klik of submit).
4. Maak een verandering zichtbaar met:
   - `classList.add()` en `classList.remove()` (bij voorkeur), of
   - aanpassen van `textContent` of `style` (als het anders niet lukt).
5. Voor formulieren: voorkom dat de pagina direct ververst als je een bericht toont (bijvoorbeeld met `event.preventDefault()`).
6. Test op minimaal 2 pagina's of op 1 pagina met meerdere interacties.

Als je klaar bent met dit deel:

1. Zet een korte notitie bij de interacties: “werkt dit op klik/submit?”
2. Maak 2 screenshots of 1 screenshot per interactie.


## Deel 3 – Stappenplan controle

| Stap | Wat doe je? | Bewijs / check |
|------|-------------|----------------|
| 1 | Je hebt JavaScript gekoppeld aan je pagina. | Interactie werkt bij laden. |
| 2 | Je hebt minstens 2 interacties. | Je kunt ze alle 2 laten zien. |
| 3 | Je gebruikt selectors om elementen te vinden. | Je code bevat `querySelector` of `getElementById`. |
| 4 | Je gebruikt eventlisteners. | Je code bevat `addEventListener`. |
| 5 | Je verandering is zichtbaar voor de gebruiker. | Je ziet menu/bericht/tekst veranderen. |
| 6 | Je code heeft geen grote fouten bij testen. | Console heeft geen duidelijke kapotte errors (als jullie dat checken). |


## Eigen aanpak mag ook!

Dit stappenplan helpt op weg, maar je mag andere interacties kiezen als het doel duidelijk is en het werkt.

**Belangrijk is dat:**

- je minstens 2 interacties maakt die je kunt testen in de browser;
- je code leesbaar blijft: per interactie een kleine duidelijke functie of blok;
- je geen grote herbouw doet als opbouw al werkt;
- je kunt uitleggen wat er gebeurt bij een klik of submit.


## Beoordeling – Rubric YourApp JavaScript

| Aspect | 0 punten (onvoldoende) | 1 punt (voldoende) | 2 punten (goed) |
|--------|------------------------|-------------------|------------------|
| Interactie werkt | Geen of maar 1 interactie werkt. | 2 interacties werken deels. | Minstens 2 interacties werken helemaal. |
| JavaScript aanpak | Code is onduidelijk of fout. | Code werkt, maar is rommelig. | Code is overzichtelijk en klopt met DOM/events. |
| Gebruik voor gebruiker | Verandering is niet zichtbaar. | Zichtbaar maar niet duidelijk. | Zichtbaar en logisch voor de gebruiker. |

**Beoordeling:**

- **Maximumscore:** 6 punten
- **Suggestie normering:**
  - 5 tot 6 punten: goed
  - 3 tot 4 punten: voldoende
  - 0 tot 2 punten: onvoldoende


## Inleveren

1. Laat je 2 interacties kort zien aan de docent (klikdemonstratie).
2. Lever digitaal in: `script.js` (of je script in HTML), screenshots en korte toelichting.

Pas als je twee interacties werken en de docent het ziet, is de Challenge afgerond.

