# web-pokus

Prototyp webu dílny zakázkového čalounění autosedadel (pracovní název značky **Sedlář**, dříve Cars Volant).

## Než začneš dělat cokoli s UI
1. Přečti `DESIGN.md` v kořeni repozitáře. Je to závazný design systém (barvy, písma, komponenty, tón textů).
2. Když se zadání a `DESIGN.md` rozcházejí, platí zadání uživatele. Pak navrhni úpravu `DESIGN.md`.

## Struktura
- `index.html` – celá stránka (HTML + CSS + JS). Three.js a GSAP se načítají z CDN (jsdelivr).
- `textures.js` – textury materiálů jako data URI (zdroj a licence v `CREDITS.md`).
- `DESIGN.md` – design systém ve formátu awesome-design-md.

## Obsah, který musí zůstat (ze specifikace)
Hero, scroll proměna před/po (GSAP ScrollTrigger + clip-path), 3D konfigurátor (zóny, materiály, barvy, prošití, logo, šablony dle značek, export + poptávka, AI nahrání fotek jako fáze 2), řemeslo a detaily materiálů, realizace s filtrem dle značek, pobočky Třebíč a Rumburk s rezervací konzultace.
