# Extra instructies en leersteun

Dit bestand hoort bij `Challenge.md` in dezelfde map.

## Korte samenvatting

Leerlingen bouwen de opmaak van YourApp met **CSS**. Ze koppelen CSS aan HTML, maken knoppen en kaarten consistent en zorgen voor een basis **responsive** opmaak met een media query. Ze leveren CSS en screenshots in.


## Waar uitleg nodig is

1. **Probleem:** Koppelen van CSS werkt niet (stijl blijft achterwege).  
   **Mini-uitleg / leerdoel:** Ze controleren of het pad en bestandsnaam in `<link>` klopt.
2. **Probleem:** Onzekerheid over selectors: `class` vs `id`.  
   **Mini-uitleg / leerdoel:** Ze gebruiken `.klassennaam` bij class en `#id-naam` bij id.
3. **Probleem:** Layout blijft rommelig omdat er geen spacing/box model aandacht is.  
   **Mini-uitleg / leerdoel:** Ze gebruiken `padding` en `margin` en testen in de browser.
4. **Probleem:** Responsive met media query lukt niet of werkt omgekeerd.  
   **Mini-uitleg / leerdoel:** Ze gebruiken één media query met een duidelijke breedte (bijv. `max-width`).
5. **Probleem:** Tekst of knoppen overlappen bij smalle schermen.  
   **Mini-uitleg / leerdoel:** Ze passen breedte en layout aan in de media query.


## Instructies (voor docent of leerling)

### 1) CSS koppelen aan je HTML controleren

1. Check in je HTML of je dit gebruikt: `<link rel="stylesheet" href="style.css">` (of vergelijkbaar).
2. Check of `style.css` exact dezelfde naam heeft als in je `href`.
3. Open je pagina in de browser en kijk of de stijl meteen zichtbaar is.

**Check:** Als je CSS wijzigt, zie je meteen effect op de pagina.


### 2) Snelle consistente stijl: gebruik een vaste aanpak

1. Maak in je CSS een blok voor `:root` met je basis kleuren en lettergroottes.
2. Maak regels voor je hoofdonderdelen: `header`, `nav`, `main`, `footer`.
3. Maak 1 set regels voor knoppen en hergebruik die op alle pagina's.

**Check:** Je ziet dezelfde kleur en afstand op meerdere pagina's.


### 3) Responsive met één media query (simpel starten)

1. Kies een breekpunt, bijvoorbeeld `max-width: 600px`.
2. Zet in je media query alleen 2 tot 4 veranderingen, zoals: menu wordt smaller of elementen stapelen.
3. Test door je browservenster te verkleinen en maak screenshots.

**Check:** Op smalle breedte is de tekst nog leesbaar en gebeurt er minder overlap.

