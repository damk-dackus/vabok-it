# Extra instructies en leersteun

Dit bestand hoort bij `Challenge.md` in dezelfde map.

## Korte samenvatting

Leerlingen ontwerpen op papier en bouwen daarna een **statisch game-HUD**: levensbalk, munten of score, en een inventarisraster met **zeldzaamheidskleuren**. Alles met **HTML en CSS** op een Windows-laptop; geen JavaScript. De opdracht past bij **VMBO**, ongeveer één les, en sluit aan bij idee **3** uit `modules/vmbo/opdrachtideeen-gaming-html-css.md`.

## Waar uitleg nodig is

1. **Probleem:** Leerlingen weten niet wat een **HUD** is.  
   **Mini-uitleg / leerdoel:** Ze kunnen in één zin zeggen dat het het **informatiepaneel** bovenop het spel is.

2. **Probleem:** Ze weten niet hoe je een **.html**-bestand **opent** in de browser.  
   **Mini-uitleg / leerdoel:** Ze openen het bestand via **dubbelklik** of **slepen** naar Edge/Chrome en zien hun eigen pagina.

3. **Probleem:** Ze kiezen geen echte **levensbalk** maar alleen tekst “100 HP”.  
   **Mini-uitleg / leerdoel:** Ze gebruiken **`<meter>`** of een `div` met **breedte** en **achtergrondkleur** als zichtbare balk.

4. **Probleem:** **CSS Grid** of **Flexbox** is nieuw; het raster wordt een lange lijst onder elkaar.  
   **Mini-uitleg / leerdoel:** Ze maken een **raster** met meerdere kolommen (bijvoorbeeld `grid-template-columns: repeat(3, 1fr)`).

5. **Probleem:** Alle items zien er hetzelfde uit; **zeldzaamheid** ontbreekt.  
   **Mini-uitleg / leerdoel:** Ze koppelen **minstens drie CSS-classes** aan drie namen (normaal / zeldzaam / superzeldzaam) met **andere kleur of rand**.

6. **Probleem:** Ze slaan op als Word of rich text; de browser toont **tags** of raar tekst.  
   **Mini-uitleg / leerdoel:** Ze slaan op als **platte tekst** met eindiging **.html** (Kladblok of code-editor).

## Instructies (voor docent of leerling)

### HUD in 30 seconden uitleggen

1. Laat **één** screenshot uit een game zien (bijvoorbeeld met levens, score, mini-map of items).  
2. Zeg: “Alles wat je **tijdens het spelen** blijft zien, heet vaak **HUD**. Jullie maken zo’n scherm **na**; het hoeft **niet** te bewegen.”  
3. Wijs aan: “Levens **balk**, hier **munten**, hier **vakjes** voor spullen.”

**Check:** Een leerling kan zonder hulp aanwijzen waar **levens**, **munten** en **items** op jullie referentie staan.

### Bestand opslaan en openen als webpagina

1. Open **Kladblok** of **VS Code**.  
2. Plak of typ je HTML en CSS.  
3. Kies **Opslaan als** en zet **type** op **Alle bestanden (*.*)** als dat nodig is.  
4. Geef de naam **game-hud.html** (of een andere naam die eindigt op **.html**).  
5. Dubbelklik het bestand of sleep het naar **Edge** / **Chrome**.

**Check:** Je ziet je **eigen titel** en kleuren in het browservenster, geen tekst met `<%` of hele regels code als letterlijke tekst (tenzij je iets per ongeluk in `<pre>` zet).

### Levensbalk met `<meter>` (simpel)

1. In de `<body>` zet je bijvoorbeeld: `<label>Levens <meter value="7" max="10"></meter></label>`.  
2. Pas `value` en `max` aan naar **eigen getallen** (bijvoorbeeld 60 en 100).  
3. Wil je **meer kleur**: gebruik CSS op `meter` als je docent dat toestaat (mag ook later als extra).

**Check:** Je ziet een **gekleurde balk** of gevulde meter naast het woord “Levens”.

### Inventarisraster met CSS Grid (basis)

1. Zet de vakjes in HTML in één **container**, bijvoorbeeld `<div class="inventory">` met daarin zes `div`-kindjes.  
2. In CSS: `.inventory { display: grid; grid-template-columns: repeat(3, 1fr); gap: 8px; }`.  
3. Geef elk vakje `min-height` (bijvoorbeeld **80px**) en een **rand** zodat je het raster ziet.

**Check:** Je ziet **drie kolommen** en **twee rijen** (of een ander raster met **minstens zes** duidelijke vakken).

### Drie zeldzaamheids-stijlen

1. Bedenk drie **klassenamen**, bijvoorbeeld `.item-normal`, `.item-rare`, `.item-epic`.  
2. Zet in CSS per class een **andere** `background-color` en voeg eventueel `border` toe (epic: **dikkere** rand of **gouden** kleur).  
3. Geef **minstens één** vakje per class in je HTML met `class="item-normal"` enzovoort.

**Check:** Op je screenshot zie je **drie** duidelijk verschillende vak-stijlen, niet alleen andere tekst.

### Als het “niet werkt”

1. Controleer of elk **geopende** `<div>` of `<section>` weer **gesloten** is.  
2. Controleer of je CSS tussen `<style>` en `</style>` staat **of** in een gekoppeld `.css`-bestand (mag als de docent dat toestaat).  
3. Gebruik **F12** in de browser alleen onder begeleiding om te zoeken naar fouten (optioneel).

**Check:** De pagina laadt **zonder** wit scherm door een kapotte tag in het eerste stukje HTML (docent helpt eventueel eenmalig).
