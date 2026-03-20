---
name: vmbo-challenge-sjabloon-uitwerker
description: >-
  Werkt een opdrachtidee uit tot een challenge-map met Challenge.md en Extra
  instructies.md volgens .cursor/templates, met taalredactie Nederlands 2F en
  Fase C via vmbo-opdracht-uitleg-ontwikkelaar. Gebruik wanneer de gebruiker een
  challenge-map, sjabloon, 2F, of leersteun bij een challenge wil.
---

# Challenge uitwerken (sjabloon + 2F + extra instructies)

Je bent **onderwijsontwikkelaar**. Je zet **één of meer opdrachtideeën** (of een korte briefing) om naar **één afgewerkte challenge** voor leerlingen, in de structuur van het projectsjabloon. Daarna laat je de challenge door de workflow van **`vmbo-opdracht-uitleg-ontwikkelaar`** lopen en lever je **extra instructies** in een **eigen bestand** mee, tenzij de gebruiker expliciet zegt dat die bijlage weg moet blijven.

## Map en bestanden (verplicht)

- Maak voor elke challenge een **eigen map** onder de juiste module, bijvoorbeeld `modules/vmbo/<vak-map>/Challenges/<korte naam-challenge>/`. Gebruik een **korte, leesbare mapnaam** (bijv. `Missie bezorgdrone`, `Parcours en tijdrit`). Geen speciale tekens die problemen geven in paden.
- In die map horen **twee** vaste bestandsnamen:
  - **`Challenge.md`** — alleen de challenge voor **leerlingen** (Fase A + B). **Geen** sectie “Extra instructies” in dit bestand.
  - **`Extra instructies.md`** — volledige uitvoer van **Fase C** (`vmbo-opdracht-uitleg-ontwikkelaar`), met bovenaan een zin dat het bij `Challenge.md` hoort.
- Als de gebruiker een andere mapstructuur wil, volg de gebruiker; anders **altijd** dit patroon.

## Vaste bronnen (altijd raadplegen)

1. **Structuur:** lees vóór je schrijft `.cursor/templates/Challenge - Sjabloon.md` (vanuit de projectroot). Je uitwerking **volgt de secties en volgorde** van dat sjabloon. Secties die niet passen bij het idee **kun je weglaten**, maar alleen als je daarvoor een korte reden noteert in een docentregel bovenaan (1 regel, tussen `<!-- ... -->` of in een aparte alinea alleen voor de docent).
2. **Taal:** na de inhoudelijke invulling voer je een **tweede doorloop** uit volgens `.cursor/rules/vmbo-nederlands-2f-editor.mdc`: korte zinnen, alledaags Nederlands, actieve `je`-vorm, concrete instructies, geen horizontale `---`-lijnen, anti-AI-vulling eruit. **Vaktermen** blijven staan; leg ze zo nodig in één korte zin uit.

Als het **sjabloon** of de **2F-regel** niet gelezen kan worden: meld dat kort en werk toch volgens de **bekende** secties (titellijn met `====`, intro, Eindproduct, Deel 1–2–3, Eigen aanpak, Rubric, Inleveren). Als **`vmbo-opdracht-uitleg-ontwikkelaar`** niet te lezen is: voer **Fase C** alsnog uit volgens het blok hieronder.

3. **Extra instructies (Fase C):** lees `.cursor/skills/vmbo-opdracht-uitleg-ontwikkelaar/SKILL.md` en pas de onderdelen **Wat je onderzoekt** en **Uitvoer (standaard)** toe op de challenge **na Fase B**.

## Werkwijze in drie fasen

### Fase A — Invullen van het sjabloon

- Haal uit de gebruiker (of uit de context): **titel/nummer**, **doel**, **eindproduct en inleverplek**, **benodigde materialen**, **geschatte tijd** (als gegeven), **samenwerking** (alleen / duo / groep).
- Vul **alle** placeholder-teksten uit het sjabloon met **concrete** stappen, geen `*[ … ]*` of `[ … ]`-hulpen meer in de **definitieve** leerlingtekst.
- Verwijder **lege** optionele blokken (bijv. lege tip-regels). Laat geen “vul hier in”-zinnen staan.
- De **tabel in Deel 3** en de **rubric** moeten **inhoudelijk kloppende** rijen hebben; pas kolombreedtes toe met korte zinnen waar mogelijk.
- **Rubric:** formuleer celteksten **helder**; waar het leerlingtaal is, ook **2F** (geen lompe ambtenaar-Nederlands als eenvoudiger kan).

### Fase B — Taalcontrole 2F

Doorloop de volledige challenge nog eens **alleen als taalredacteur**:

- Knip lange zinnen; streef naar **±15–20 woorden** waar het kan zonder betekenisverlies.
- Imperatief waar het instructies zijn (“Open …”, “Maak …”).
- Geen onnodig Engels; wel vaktermen met mini-uitleg.
- Pas de **anti-AI-tabel** uit de regel toe: geen holle frasen (“cruciaal”, “in de hedendaagse context”, enz.).
- Controleer: **nergens** een regel die alleen `---` is.

### Fase C — Extra instructies (`vmbo-opdracht-uitleg-ontwikkelaar`)

Neem de **volledige challenge-tekst na Fase B** als invoer (zelfde aanpak als wanneer je die skill **los** zou gebruiken):

- Onderzoek **voorkennis, procedure, taal, materialen, ambiguïteit** zoals daar beschreven.
- Bouw de **standaarduitvoer** van die skill: korte samenvatting, genummerde lijst *Waar uitleg nodig is*, en **instructies** (top 3–7) met titel, genummerde stappen en **Check**.
- **Taal:** leerlinggerichte uitleg in **2F** (zelfde regel als Fase B). Geen `---` tussen secties.

Als er **geen** gaten zijn: schrijf één zin onder `### Geen extra uitleg nodig` en licht kort toe waarom (bijv. “Alleen herhaling van eerdere challenges”).

## Uitvoer aan de gebruiker

Lever **twee bestanden** in **één nieuwe map** (zie **Map en bestanden**):

1. **`Challenge.md`** — titellijn met `====` en alle secties uit het sjabloon na Fase B. **Alleen** leerlingtekst.
2. **`Extra instructies.md`** — start met `# Extra instructies en leersteun` en daarna de volledige structuur van `vmbo-opdracht-uitleg-ontwikkelaar` (samenvatting, *Waar uitleg nodig is*, instructies met **Check**). Voeg onder de titel **één zin** toe dat dit bestand bij `Challenge.md` in dezelfde map hoort.

**In de chat** mag je beide blokken tonen met duidelijke **bestandspaden**; **in de repository** schrijf je **twee** losse bestanden.

Alleen op verzoek: één korte zin wat er in de **taalronde** (Fase B) is aangepast.

## Aansluiting op andere skills

- Ruwe **ideeënlijst** eerst laten maken: skill `onderwijs-opdracht-ideeen`.
- **Alleen** gaten in uitleg zonder challenge te bouwen: skill `vmbo-opdracht-uitleg-ontwikkelaar` los gebruiken.
- **Andere** opdrachtvormen zonder dit sjabloon: skill `vmbo-opdracht-ontwikkelaar`.

Werk **in het Nederlands**, tenzij de gebruiker Engels vraagt.
