---
title: "Logo ja värit – Suomen Palikkaharrastajat ry"
description: "Suomen Palikkaharrastajat ry:n logo ja visuaalinen identiteetti"
slug: index
published: true
nav: mobile
navTitle: "Logo ja värit"
order: 0
---

## Logot

<asset-gallery source="logos-square" title="Neliö" description="Hymyilevä minihahmon pää rakennuspalikoista koottuna. Sopii someen ja sovelluskuvakkeisiin."/>

<asset-gallery source="logos-square-full" title="Neliö tekstillä" description="Hymyilevä logo kahdella tekstirivillä alla. Käytä kun tarvitset täydellisen tunnuksen pystysuuntaisessa asettelussa."/>

<asset-gallery source="logos-horizontal" title="Vaakasuuntainen" description="Neljä minihahmon päätä vierekkäin. Vaakaversio tekstillä sopii esitteisiin ja nettisivuille."/>

## Logon käyttö

<info-panel color="amber" title="Käyttöohjeet">

- Käytä SVG ensin; WebP PNG-varaversiolla
- Älä venytä, litistä tai värjää logon osia
- Älä käytä animoitua logoa tulostettavissa tai sähköpostissa

**Minimikoko:** 80 px (neliö) · 200 px (vaaka) · **Tyhjä tila:** vähintään 25 % logon leveydestä joka suuntaan

</info-panel>

### Mikä logo mihinkin?

| Konteksti | Suositeltu variantti | Formaatti |
|---|---|---|
| Sivun header / navigaatio | square-smile-full tai horizontal-full | SVG |
| Tumma header / footer | square-smile-full-dark tai horizontal-full-dark | SVG |
| Sosiaalinen media / OG-kuva | horizontal-full | PNG (1200 × 630) |
| Favicon (selain) | favicon.ico + favicon-32.png | ICO + PNG |
| PWA / kotinäyttö (Android) | icon-192.png, icon-512.png | PNG |
| iOS kotinäyttö | apple-touch-icon.png (180 px) | PNG |
| Painotuotteet | horizontal-full tai square-smile-full | SVG tai 300 dpi+ PNG |
| Animoitu banneri / hero | square-animated / horizontal-full-animated | WebP/GIF (ei reduced-motion -käyttäjille) |

### Koodiesimerkit

Favicon — `<head>`:

```html
<link rel="icon" href="/favicon/favicon.ico" sizes="any">
<link rel="icon" href="/favicon/favicon-32.png" type="image/png" sizes="32x32">
<link rel="icon" href="/favicon/favicon-48.png" type="image/png" sizes="48x48">
<link rel="apple-touch-icon" href="/favicon/apple-touch-icon.png">
<link rel="manifest" href="/site.webmanifest">
```

Logo — `<picture>` WebP + PNG:

```html
<picture>
  <source
    srcset="/logo/horizontal/png/horizontal-full.webp"
    type="image/webp">
  <img
    src="/logo/horizontal/png/horizontal-full.png"
    alt="Suomen Palikkaharrastajat ry"
    width="400" height="120">
</picture>
```

## Värit

Kaikki värit on määritelty suunnittelutokeneina tiedostossa `vendor/design-guide/content/colors.toml` ja generoitu Elm-moduuliksi `DesignTokens.Colors`. CSS-muuttujat löytyvät tiedostosta `style.css`.

<color-grid source="brand" title="Brändivärit" description="Yhdistyksen kolme pääväriä."/>

| Nimi | Koodi | CSS-muuttuja | Tailwind-luokka |
|---|---|---|---|
| LEGO Black | `#05131D` | `--color-brand` | `bg-brand` / `text-brand` |
| Skin Tone Yellow | `#FAC80A` | `--color-brand-yellow` | `bg-brand-yellow` / `text-brand-yellow` |
| Red | `#C91A09` | `--color-brand-red` | `text-brand-red` |

<color-grid source="skin-tones" title="Ihonsävypaletti (Nougat)" description="Lämpimät korostusvärit, jotka perustuvat LEGO-minifiguurien ihonsävyihin."/>

| Nimi | Koodi | CSS-muuttuja | Tailwind-luokka |
|---|---|---|---|
| Light Nougat | `#F6D7B3` | `--color-brand-nougat-light` | `bg-brand-nougat-light` |
| Medium Nougat | `#D09168` | `--color-brand-nougat` | `bg-brand-nougat` |
| Dark Nougat | `#AD6140` | `--color-brand-nougat-dark` | `bg-brand-nougat-dark` |

<color-grid source="rainbow" title="Sateenkaarispektri" description="Lisävärit brändikäyttöön — esim. tapahtumien teemavärit ja kuvitukset."/>

| Nimi | Koodi | Käyttö |
|---|---|---|
| Salmon | `#FE5E52` | Lämmin korostus |
| Orange | `#FE8A18` | Energinen korostus |
| Yellow | `#FAC80A` | = Brändi-keltainen |
| Green | `#00852B` | Positiiviset tilat |
| Blue | `#0055BF` | Informatiiviset tilat |
| Lilac | `#9391E4` | Leikkisä korostus |
| Lavender | `#E4ADC8` | Pehmeä korostus |

### Semanttiset väritokenit

Nämä tokenit abstrahoivat käyttötarkoituksen erilleen raa'asta väristä:

#### Teksti

| Token | Arvo | Käyttö |
|---|---|---|
| `text-primary` | `#05131D` | Otsikot, leipäteksti |
| `text-on-dark` | `#FFFFFF` | Teksti tummalla taustalla |
| `text-muted` | `#6B7280` | Toissijaiset kuvaukset |
| `text-subtle` | `#9CA3AF` | Paikanpitäjät, kuvatekstit |

#### Taustat

| Token | Arvo | Käyttö |
|---|---|---|
| `bg-page` | `#FFFFFF` | Sivun tausta |
| `bg-subtle` | `#F9FAFB` | Korttien ja paneelien tausta |
| `bg-accent` | `#FAC80A` | Korostus- ja CTA-taustat |
| `bg-dark` | `#05131D` | Navigaatio, footer |

#### Reunat

| Token | Arvo | Käyttö |
|---|---|---|
| `border-default` | `#E5E7EB` | Oletusreunat, erottimet |
| `border-brand` | `#05131D` | Brändivärinen reuna |

### Käyttö Elm-koodissa

Semanttiset värit ovat käytettävissä `TailwindTokens`-moduulin kautta:

```elm
import Tailwind as Tw exposing (classes)
import TailwindTokens as TC

-- Tausta ja teksti
classes [ Tw.bg_simple TC.brand, Tw.text_simple TC.textOnDark ]

-- Reuna
classes [ Tw.border_simple TC.borderDefault ]

-- Korostus
classes [ Tw.bg_simple TC.brandYellow, Tw.text_simple TC.textPrimary ]
```

### Käyttö CSS/HTML:ssä

```html
<!-- Semanttiset Tailwind-luokat -->
<div class="bg-brand text-text-on-dark">
  Tumma tausta, valkoinen teksti
</div>

<div class="bg-bg-subtle border border-border-default">
  Korttipohja
</div>

<button class="bg-brand-yellow text-brand hover:opacity-90">
  Toimintopainike
</button>
```

<callout type="warning">

**Älä kovakoodaa heksavärejä** — käytä aina Tailwind-luokkia semanttisilla nimillä. Näin värien päivitys tapahtuu yhdestä paikasta.

</callout>
