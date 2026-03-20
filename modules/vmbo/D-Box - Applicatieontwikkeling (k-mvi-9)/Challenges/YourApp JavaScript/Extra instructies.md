# Extra instructies en leersteun

Dit bestand hoort bij `Challenge.md` in dezelfde map.

## Korte samenvatting

Leerlingen voegen **JavaScript-interactie** toe aan YourApp. Ze kiezen minstens 2 interacties en maken die zichtbaar met eventlisteners en DOM-manipulatie (bijv. klasse wisselen of tekst aanpassen). Er is geen framework nodig; plain JavaScript is genoeg.


## Waar uitleg nodig is

1. **Probleem:** Leerlingen weten niet wat een `event` is (bijv. klik, submit).  
   **Mini-uitleg / leerdoel:** Ze kunnen uitleggen dat een event gebeurt als iemand klikt of iets invult.
2. **Probleem:** Elementen vinden lukt niet door verkeerde selector.  
   **Mini-uitleg / leerdoel:** Ze gebruiken `id` met `getElementById` of `class` met `querySelector`.
3. **Probleem:** Menu of tekst blijft niet zichtbaar/verborgen.  
   **Mini-uitleg / leerdoel:** Ze gebruiken CSS-klassen (`classList`) en checken of CSS ook echt die klasse gebruikt.
4. **Probleem:** Formulieren sturen pagina weg en verdwijnen het bericht.  
   **Mini-uitleg / leerdoel:** Ze gebruiken `event.preventDefault()` bij submit.
5. **Probleem:** Code staat op de verkeerde plek of wordt niet ingeladen.  
   **Mini-uitleg / leerdoel:** Ze controleren dat het script bestandspad klopt en dat het script werkt bij het laden.


## Instructies (voor docent of leerling)

### 1) Opdracht starten met een “klik -> zichtbaarheid” voorbeeld

1. Kies 1 element dat je kan tonen/verbergen, bijvoorbeeld een `<div>` met uitleg.
2. Geef dat element een `id`, bijvoorbeeld `extra-info`.
3. Koppel een knop met een `id`, bijvoorbeeld `btn-extra`.
4. In JavaScript: kies beide elementen en maak op klik een verandering zichtbaar (bijv. een klasse toevoegen/verwijderen).

**Check:** Bij klikken zie je direct verandering in de browser.


### 2) Menu/bericht: liever via CSS-klassen dan via style

1. Maak in CSS een “open” variant voor je component (bijv. `.menu-open`).
2. Laat JavaScript alleen de klasse wisselen met `classList.add()` en `classList.remove()`.
3. Test of de CSS echt gekoppeld is aan de klasse.

**Check:** Je hoeft minder te sleutelen aan individuele CSS-eigenschappen.


### 3) Formulier submit: bericht tonen zonder refresh

1. Voeg in je JavaScript een eventlistener toe op het formulier (submit).
2. In de submit-functie: gebruik `event.preventDefault()`.
3. Zet daarna je bericht in `textContent` of toon een `<div>` die al bestaat.

**Check:** Na verzenden blijft de pagina staan en zie je het bericht.

