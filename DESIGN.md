---
version: 0.1
name: Sedlar-design-system
description: Tichý, řemeslný vzhled pro dílnu zakázkového čalounění automobilových interiérů. Téměř černé teplé plátno, realisticky renderovaná sedadla jako jediný zdroj „barvy“, velká písmena s širokým prostrkáním, patkový text pro vyprávění a strojově přesné popisky v monospace. Žádné gradienty, stíny ani dekorace. Značka nekřičí „prémiově“, prostě působí draze.

colors:
  canvas: "#0e0d0c"
  surface: "#161412"
  surface-raised: "#1d1a17"
  hairline: "#2a2622"
  hairline-strong: "#3d3731"
  ink: "#ece6dd"
  body: "#c9c1b6"
  muted: "#8f877c"
  muted-soft: "#625b53"
  accent: "#a8784a"        # koňak, jediný akcent, jen pro vybraný stav a nit
  on-accent: "#0e0d0c"
  error: "#c0614f"
  success: "#7f9a6a"

typography:
  display-xl: { fontFamily: "Manrope", fontSize: "clamp(40px, 6vw, 76px)", fontWeight: 400, lineHeight: 1.05, letterSpacing: "0.06em", textTransform: uppercase }
  display-lg: { fontFamily: "Manrope", fontSize: "clamp(30px, 4vw, 46px)", fontWeight: 400, lineHeight: 1.1, letterSpacing: "0.05em", textTransform: uppercase }
  display-sm: { fontFamily: "Manrope", fontSize: 20px, fontWeight: 400, lineHeight: 1.3, letterSpacing: "0.08em", textTransform: uppercase }
  wordmark:   { fontFamily: "Manrope", fontSize: 15px, fontWeight: 500, letterSpacing: "0.42em", textTransform: uppercase }
  body-lg:    { fontFamily: "EB Garamond", fontSize: 21px, fontWeight: 400, lineHeight: 1.55 }
  body-md:    { fontFamily: "EB Garamond", fontSize: 18px, fontWeight: 400, lineHeight: 1.6 }
  label:      { fontFamily: "JetBrains Mono", fontSize: 11px, fontWeight: 400, letterSpacing: "0.16em", textTransform: uppercase }
  button:     { fontFamily: "JetBrains Mono", fontSize: 12px, fontWeight: 400, letterSpacing: "0.18em", textTransform: uppercase }

rounded:
  none: 0px
  pill: 9999px

spacing: { xs: 8px, sm: 12px, md: 16px, lg: 24px, xl: 40px, xxl: 64px, section: 140px }

components:
  button-primary:   { background: transparent, border: "1px solid {colors.ink}", text: "{colors.ink}", typography: "{typography.button}", rounded: "{rounded.pill}", padding: "15px 30px" }
  button-solid:     { background: "{colors.ink}", text: "{colors.canvas}", typography: "{typography.button}", rounded: "{rounded.pill}" }
  option-row:       { background: transparent, borderBottom: "1px solid {colors.hairline}", selected: "text {colors.ink} + 1px {colors.accent} underline" }
  swatch:           { size: 36px, rounded: "{rounded.pill}", selected: "1px ring {colors.accent} offset 3px" }
  text-input:       { background: transparent, border: none, borderBottom: "1px solid {colors.hairline-strong}", rounded: 0, focus: "border {colors.ink}" }
  render-stage:     { background: "{colors.canvas}", rounded: 0, border: none }
---

## Overview

Web dílny, ne katalog. Hlavní postavou je sedadlo, vyrenderované realisticky (Three.js, PBR materiály, studiové světlo). Všechno ostatní ustupuje: téměř černé teplé plátno, bílé písmo, jediný koňakový akcent. Inspirace: Bugatti (strohost, prostrkaná velká písmena, žádný akcent), Ferrari Tailor Made (řemeslo, detail materiálu), Hermès (ruční práce vyprávěná patkovým písmem).

**Hlas značky:** klidný a věcný. Nepoužíváme slova „prémiový“, „luxusní“, „exkluzivní“, „špičkový“. Kvalitu ukazujeme detailem (počet stehů na centimetr, původ kůže, doba práce), ne přívlastky. Oslovujeme lidi, kteří nic nedokazují.

**Klíčové vlastnosti**
- Jeden tmavý motiv na celé stránce. Žádné přepínání světlých a tmavých sekcí.
- Hloubku dělá jen render nebo fotografie. Žádné stíny, gradientní pozadí ani skleněné efekty.
- Tři písma a každé má jednu roli: **Manrope** (nadpisy, velká písmena, váha 400), **EB Garamond** (text), **JetBrains Mono** (popisky, tlačítka, čísla).
- Zaoblení je binární: 0 px všude, pilulka jen u tlačítek a vzorníků barev.
- Akcent `#a8784a` jen pro vybraný stav, nit v renderu a zaměření. Nikdy jako plocha.

## Colors

| Token | Hex | Použití |
|---|---|---|
| canvas | #0e0d0c | Pozadí celé stránky |
| surface | #161412 | Panel konfigurátoru, formulář |
| hairline | #2a2622 | Dělicí čáry, řádky voleb |
| ink | #ece6dd | Nadpisy, hlavní text, obrys tlačítek |
| body | #c9c1b6 | Odstavce |
| muted | #8f877c | Popisky, metadata |
| accent | #a8784a | Vybraný stav, nit, focus |

## Typography

- Nadpisy vždy VELKÝMI písmeny, váha 400, prostrkání 0,05 až 0,08 em. Důraz dělá velikost a prostrkání, nikdy tučné písmo.
- Text v EB Garamond, 18 až 21 px, max. 62 znaků na řádek.
- Popisky, ceny, tlačítka a navigace v JetBrains Mono, 11 až 12 px, velká písmena.
- Všechna tři písma umí českou diakritiku (latin-ext).

## Layout

- Max. šířka obsahu 1240 px, render a before/after přes celou šířku.
- Mezi sekcemi 140 px. Hodně prázdného místa, je to součást značky.
- Hero rozdělený: text vlevo, render vpravo. Nadpis max. 2 řádky, podtext max. 20 slov.
- Na mobilu (< 768 px) vše v jednom sloupci, boční okraj 16 px.
- Žádné tři stejné karty vedle sebe. Galerie jako asymetrická mřížka (jedna velká položka, zbytek menší).

## Elevation & Depth

Plochá stránka. Hloubka jen z renderu (studiové osvětlení, kontaktní stín pod sedadlem). Karty nemají stín ani rámeček, oddělují je mezery nebo 1px `hairline`.

## Components

- **Tlačítko primární:** průhledné, 1px obrys `ink`, pilulka, mono popisek. **Plné** (`ink` na `canvas`) jen pro jednu hlavní akci na obrazovce (Odeslat poptávku).
- **Volby konfigurátoru:** řádky oddělené hairline, ne čipy. Vybraná volba = `ink` text + koňakový podtržítkový pruh.
- **Vzorník barev:** kruh 36 px, vybraný má koňakový prstenec s odsazením.
- **Pole formuláře:** jen spodní linka, popisek nad polem (mono), chyba pod polem v `error`.
- **Render stage:** bez rámečku, splývá s plátnem. Ovládání (otočit, přiblížit) jako malé kruhové ikony s obrysem.

## Motion

- Scroll animace jen v sekci Proměna (GSAP ScrollTrigger, odkrytí přes `clip-path: inset()`).
- Ostatní: jemné nabíhání (opacity + translateY 12 px, 600 ms).
- Respektovat `prefers-reduced-motion`: bez animací, Proměna se ovládá posuvníkem.

## Do's and Don'ts

- ✅ Konkrétní fakta místo přívlastků („14 stehů na 10 cm“, „kůže z garbovny v Itálii“).
- ✅ Ukázková data jasně označit jako ukázka.
- ❌ Slova prémiový, luxusní, exkluzivní, špičkový, wow.
- ❌ Zlaté gradienty, lesklé efekty, fialová, neonová záře.
- ❌ Tučné nadpisy, zaoblené karty, stíny.
