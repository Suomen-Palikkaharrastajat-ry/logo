---
title: "Typografia"
description: "Typografiaskaala, fonttiohjeet ja ikonien käyttö suunnittelujärjestelmässä."
slug: typografia
published: true
nav: true
navTitle: "Typografia"
order: 1
---

# Typografia

Fontti: **Outfit** (variable, painot 100–900), itseisännöity `/fonts/`-hakemistosta. Älä koskaan korvaa toisella fontilla.

Käytä aina nimettyjä `type-*` -apuluokkia, jotka on määritelty `style.css`-tiedostossa. Älä käytä raakoja Tailwind-koko/paino-yhdistelmiä.

---

## Typografiaskaala

| Luokka | Koko | Paino | Rivikorkeus | Käyttö |
|---|---|---|---|---|
| `type-display` | 3rem (48px) | 700 | 1.1 | Hero-otsikot, vain ≥ md |
| `type-h1` | 1.875rem (30px) | 700 | 1.2 | Sivun pääotsikko (yksi per sivu) |
| `type-h2` | 1.5rem (24px) | 700 | 1.3 | Osio-otsikot |
| `type-h3` | 1.25rem (20px) | 600 | 1.35 | Alaosio-otsikot |
| `type-h4` | 1.125rem (18px) | 600 | 1.4 | Kortti-/widget-otsikot |
| `type-body` | 1rem (16px) | 400 | 1.6 | Oletusleipäteksti |
| `type-body-small` | 0.875rem (14px) | 500 | 1.5 | Käyttöliittymäkontrollit, nimiöt |
| `type-caption` | 0.875rem (14px) | 400 | 1.4 | Kuvatekstit, alaviitteet |
| `type-mono` | 0.875rem (14px) | 400 | 1.6 | Koodinäytteet (tasalevyinen) |
| `type-overline` | 0.75rem (12px) | 600 | 1.4 | Kategorianimiöt (ISOT KIRJAIMET) |

---

## Käyttöohjeet

### Tee näin ✓

- Käytä `type-h2` osio-otsikoihin ja `type-body` leipätekstiin
- Käytä `type-overline` kategorianimiöihin
- Noudata otsikkohierarkiaa: h1 → h2 → h3 → h4
- Käytä `type-display` vain vähintään `md`-koossa (768 px)
- Käytä `type-mono` heksaväreille ja CSS-muuttujille

### Älä tee näin ✗

- Älä käytä raakoja Tailwind-luokkia kuten `text-2xl font-bold`
- Älä hyppää otsikkotasoja (esim. h1 → h3 ilman h2:ta)
- Älä aseta html-elementin fonttikokoa
- Älä korvaa Outfit-fonttia toisella
- Älä käytä `type-caption` alle 14 px:n koossa

---

## CSS-esimerkki

```html
<!-- Oikein: käytä type-* luokkia -->
<h1 class="type-h1">Sivun otsikko</h1>
<p class="type-body">Leipäteksti käyttää oletuskokoa.</p>
<span class="type-overline">KATEGORIA</span>
<code class="type-mono">#05131D</code>

<!-- Väärin: raa'at Tailwind-luokat -->
<h1 class="text-3xl font-bold">Älä tee näin</h1>
```

---

## Ikonit

Ikonikirjasto: **feathericons/elm-feather** v1.5.0. Käytä aina `FeatherIcons`-moduulia eikä omia SVG-tiedostoja.

### Käyttö Elm-koodissa

```elm
import FeatherIcons

-- Perusikoni
FeatherIcons.search |> FeatherIcons.toHtml []

-- Mukautettu koko
FeatherIcons.star
    |> FeatherIcons.withSize 32
    |> FeatherIcons.toHtml []
```

### Ikonikategoriat

**Navigointi:** menu, x, arrowUp, arrowDown, arrowLeft, arrowRight, home, search, externalLink, chevronUp, chevronDown, chevronLeft, chevronRight

**Tila:** info, alertTriangle, alertCircle, checkCircle, xCircle, check, circle, loader

**Sisältö:** calendar, clock, star, flag, users, user, mapPin, fileText, tag, link, mail, phone

**Media:** rss, camera, youtube, image, video, music

**Toiminnot:** zap, settings, edit, edit2, trash2, plus, plusCircle, minus
