# Opdrachtideeën: gaming met HTML en CSS

**Uitgangspunten:** Windows-laptop, games draaien in de browser en zijn gebouwd met **HTML en CSS** (geen game-engine).

---

## 1. Kies-je-eigen-avontuur (game met keuzes)

- Leerlingen schrijven een kort verhaal met meerdere paden (bijv. mislukt eind / goed eind). Ze bouwen dat in één of meerdere HTML-pagina’s met **links** en duidelijke koppen. Elke keuze is een link naar een andere sectie (`id` + interne links) of een andere pagina.
- **Levering:** Werkende “game” in de browser + korte legplaat (stroomschema op papier of in Draw.io).
- **Tijd:** ± 50–100 min (1–2 lesuren).

*Waarom sterk:* Duidelijke game-ervaring, leert structuur en navigatie.

---

## 2. Geheugenspel met kaarten (alleen HTML + CSS)

- Een raster met “kaarten”. Omkeren met **`:checked`** (verborgen checkbox + label) of met **`<details>`/`<summary>`** als eenvoudigere variant. Paren zoeken (icoontjes, kleuren, kleine woorden).
- **Levering:** Één `index.html` (eventueel met interne `<style>`) dat lokaal in Chrome/Edge opent.
- **Tijd:** ± 90–150 min (2–3 lesuren); variant met `<details>` sneller (~60 min).

*Waarom sterk:* Voelt als echte game, haalbaar zonder JavaScript bij de eenvoudige variant.

---

## 3. Game HUD: inventaris & statusbalk

- Geen speelbare wereld, wel een **spel-interface**: levensbalk (`<meter>` of `div` + breedte), munten, icoontjes in een raster, zeldzaamheid met **CSS-kleuren** (common/rare/epic). Statisch: “dit zou je inventaris in een RPG kunnen zijn”.
- **Levering:** Screenshot + werkende HTML-pagina.
- **Tijd:** ± 40–55 min (1 lesuur).

*Waarom sterk:* Motiverend gamer-thema, veel oefening met layout en kleur.

---

## 4. Tik-op-het-doel (reactietraining-stijl)

- “Targets” op het scherm (`div` met `:hover` / klik). Na klik: nieuwe `:target`-sectie toont score of volgend level via links met `#level2` op dezelfde pagina.
- **Levering:** Werkende mini-game in één HTML-bestand.
- **Tijd:** ± 45–60 min.

---

## 5. Pixelheld of sprite op het raster

- Personage of item opbouwen met **CSS-grid** (kleine vakjes = pixels), zoals oude games. Optioneel tweede variant “damage” met andere kleuren (twee classes).
- **Levering:** HTML + CSS, korte toelichting welke kleuren wat betekenen.
- **Tijd:** ± 50–70 min.

---

## 6. One-page arcade-stijl (alleen sfeer + animatie)

- Achtergrond met **infinite scroll**-gevoel (`animation` op herhalend patroon), titel in arcadestijl (`text-shadow`), knipperende “Press Start”-tekst.
- **Levering:** Eén pagina die eruitziet als startmenu van een game.
- **Tijd:** ± 35–50 min.

---

## 7. Bordspel op papier → HTML-raster

- Eerst bord ontwerpen (3×3 of 4×4) op papier, daarna hetzelfde in **semantische HTML** (`table` of `div` + grid) met vakjes en pionnen (CSS `border-radius`).
- **Levering:** Statisch bord + spelregels in ±5 zinnen op de pagina.
- **Tijd:** ± 50–70 min.

---

## 8. Quiz-bossfight (alleen HTML + CSS)

- Meerkeuze met **radio’s**; met **`:checked` + sibling selectors** of secties per vraag ga je stap voor stap naar “baas verslagen”. Foute keuze: link naar game-over-sectie.
- **Levering:** Lineaire of korte vertakking in één pagina.
- **Tijd:** ± 60–90 min.

---

## 9. Game-review pagina (met game-look)

- Recensie: titel, sterren (Unicode of CSS), screenshots als `figure`, tip/waarschuwing in opvallende box. Thema gaming, nadruk op HTML-structuur.
- **Tijd:** ± 40–50 min.

---

## Tip om verder uit te werken

**Meest “game” met strikt HTML/CSS:** idee **1** (avontuur) of **2** (geheugen).

Voor een volledige lesopdracht met tijdsverdeling: skill `vmbo-opdracht-ontwikkelaar` gebruiken.
