---
title: "Värit"
description: "Brändiväripaletti, semanttiset väritokenit ja kontrastiohjeet."
slug: varit
published: false
nav: false
navTitle: "Värit"
order: 5
---

# Värit

Kaikki värit on määritelty suunnittelutokeneina tiedostossa `vendor/design-guide/content/colors.toml` ja generoitu Elm-moduuliksi `DesignTokens.Colors`. CSS-muuttujat löytyvät tiedostosta `style.css`.

---

## Brändivärit

Yhdistyksen kolme pääväriä:

| Nimi | Koodi | CSS-muuttuja | Tailwind-luokka |
|---|---|---|---|
| LEGO Black | `#05131D` | `--color-brand` | `bg-brand` / `text-brand` |
| Skin Tone Yellow | `#FAC80A` | `--color-brand-yellow` | `bg-brand-yellow` / `text-brand-yellow` |
| Red | `#C91A09` | `--color-brand-red` | `text-brand-red` |

---

## Ihonsävypaletti (Nougat)

Lämpimät korostusvärit, jotka perustuvat LEGO-minifiguurien ihonsävyihin:

| Nimi | Koodi | CSS-muuttuja | Tailwind-luokka |
|---|---|---|---|
| Light Nougat | `#F6D7B3` | `--color-brand-nougat-light` | `bg-brand-nougat-light` |
| Medium Nougat | `#D09168` | `--color-brand-nougat` | `bg-brand-nougat` |
| Dark Nougat | `#AD6140` | `--color-brand-nougat-dark` | `bg-brand-nougat-dark` |

---

## Sateenkaarispektri

Lisävärit brändikäyttöön (esim. tapahtumien teemavärit, kuvitukset):

| Nimi | Koodi | Käyttö |
|---|---|---|
| Salmon | `#FE5E52` | Lämmin korostus |
| Orange | `#FE8A18` | Energinen korostus |
| Yellow | `#FAC80A` | = Brändi-keltainen |
| Green | `#00852B` | Positiiviset tilat |
| Blue | `#0055BF` | Informatiiviset tilat |
| Lilac | `#9391E4` | Leikkisä korostus |
| Lavender | `#E4ADC8` | Pehmeä korostus |

---

## Semanttiset väritokenit

Nämä tokenit abstrahoivat käyttötarkoituksen erilleen raa'asta väristä:

### Teksti

| Token | Arvo | Käyttö |
|---|---|---|
| `text-primary` | `#05131D` | Otsikot, leipäteksti |
| `text-on-dark` | `#FFFFFF` | Teksti tummalla taustalla |
| `text-muted` | `#6B7280` | Toissijaiset kuvaukset |
| `text-subtle` | `#9CA3AF` | Paikanpitäjät, kuvatekstit |

### Taustat

| Token | Arvo | Käyttö |
|---|---|---|
| `bg-page` | `#FFFFFF` | Sivun tausta |
| `bg-subtle` | `#F9FAFB` | Korttien ja paneelien tausta |
| `bg-accent` | `#FAC80A` | Korostus- ja CTA-taustat |
| `bg-dark` | `#05131D` | Navigaatio, footer |

### Reunat

| Token | Arvo | Käyttö |
|---|---|---|
| `border-default` | `#E5E7EB` | Oletusreunat, erottimet |
| `border-brand` | `#05131D` | Brändivärinen reuna |

---

## Käyttö Elm-koodissa

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

---

## Käyttö CSS/HTML:ssä

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
